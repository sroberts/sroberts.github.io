---
layout: Post
title: Effective Tagging in Synapse
date: 2023-01-20T07:00:00.000Z
draft: false
tags:
  - intelligence
---
> Analysis paralysis occurs when you overthink and underwork. — **Orrin Woodward**

So, you’re playing with [Synapse](https://github.com/vertexproject/synapse/) (or it's [commercial version](https://vertex.link/synapse)), it’s outstanding, you’ve sorted through lifting, creating data, maybe even added some Power Ups.  Chances are, you’ve learned and started seeing the genius between the idea of nodes (which represent facts) and tags (which can be used to represent countless things, but notably assessments). You’ve probably even created a few.

Possibly more than a few. It might be you’ve added numerous tags. Chances are even pretty high that now you’ve got a mess of tags. An actual mess. Too many tags, too disorganized, redundant, and difficult to remember and use. That’s not a bad thing, in fact, I’d argue it’s a key Synapse rite of passage. On the other hand, it’s not sustainable, so you need to move back towards sanity. Let’s talk about what that can look like.

## Tagging Philosophy

What likely got you into this problem in the first place was not having any philosophy of how to create and manage tags. There are three obvious schools of thought for getting started with tags:

* **Draconian:** Rigidly define tags at the start and only allow a small subset of tags. Restrict who can create new tags.
* **Lenient:** Don’t put any restrictions on it, let people tag as they like. Let individuals build their own hierarchies.
* **Middle Ground:** This could mean many things. It could mean you let senior analysts define new tags and more junior analysts apply them. Another middle ground could be having strict rules, but only monitor them via convention rather than configuration. It could mean some form of regular clean up or automation.

Which one is correct? The answer is, as always, the typical CTI answer: _It depends._ On the size of your team, the seniority of the analysts, the level of experience, all these things. The key though is to agree, to discuss it as a team, and come to an agreement.

## Tag Hierarchy

Firstly, any tagging hierarchy you choose, as long as you’re consistent, will likely be effective. There are a few different approaches:

### Cribbing from Vertex

If you read the Synapse documentation or watch their videos, you’ll see plenty of examples of their tagging philosophy. On one hand, I’ll never argue with using a tool the way the team behind it anticipates, there’s a reason they do it that way. It will likely always work effectively, and if anything they might build some niceties to support it. Picking this up will take some doing, and primarily means following their documentation, watching their videos, and asking questions in their Slack.

All things I recommend and I have done. That said, I went my own way (and one of the benefits of Synapse is supporting that!).

### Diamond Model Hierarchy

My default tagging model is based on the elegant fundamentals of the [_Diamond Model_](](https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf). Base tag (IE first level) are the core _Diamond Model_ elements.

* Adversary
* Infrastructure
* Capability
* Victim

The secondary tags are used for categories. These, I try to keep these pretty minimal (since really each of these is exponential). Let us break them down from there.

## #️⃣ Adversary

> “There exists a set of adversaries (insiders, outsiders, individuals, groups, and organizations) which seek to compromise computer systems or networks to further their intent and satisfy their needs.” — [The Diamond Model of Intrusion Analysis](https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf)

The adversary tag is one of the most complicated base tag possible because it gets into attribution/clustering, either of which is always going to be messy. I’ve approached this in a few different ways.

The `aka` is the default used by the [Synapse documentation,](https://synapse.docs.vertex.link/en/latest/synapse/userguides/analytical_model_tags.html?highlight=aka#tags-as-nodes) acknowledging that doing this sort of attribution is inherently just trusting the random assessments of others. In this case, `syn:tag=aka.feye.thr.apt1` would be tagging an indicator to say “this is also known as APT1 by Mandiant”. This is fine, and I thoroughly understand this approach, but I take a slightly different approach.

What works for me works more like this: `#adversary.<type>.<group>.<subgroup>`. Here’s a smattering of examples:

```plaintext
cli> storm --hide-props syn:tag^=adversary
Executing query at 2023/01/19 22:58:24.635
syn:tag=adversary
syn:tag=adversary.criminal
syn:tag=adversary.criminal.agenttesla
syn:tag=adversary.criminal.conti
...
syn:tag=adversary.disinformation
syn:tag=adversary.disinformation.internetresearchagency
syn:tag=adversary.espionage
syn:tag=adversary.espionage.applejeus
syn:tag=adversary.espionage.apt10
...
syn:tag=adversary.terrorist
syn:tag=adversary.terrorist.alshabaab
syn:tag=adversary.terrorist.alshabaab.amniyat
...
syn:tag=adversary.unk
syn:tag=adversary.unk.bananasulfate
syn:tag=adversary.unk.callisto
...
syn:tag=adversary.unk.ta2722
syn:tag=adversary.unk.xegroup
```

Now this is imperfect as well (hence why understand folks using `aka`, in particular when you’ve got groups that end up moonlighting in both criminal and espionage (In most cases like that I just use both depending on the context). It hasn’t been a problem that many times (Except Lazarus… it always comes back to Lazarus).

For example:

```plaintext
[ media:news=(*) :url=https://blog.malwarebytes.com/social-engineering/2022/04/north-korean-lazarus-apt-group-targets-blockchain-tech-companies/ +#adversary.criminal.lazarusgroup +#adversary.criminal.apt38 ]
```

Now to be clear, I know I’m doing something others might not do. Not only am I referring to the Lazarus Group as a criminal group, but I’m also calling the Mandiant designation of APT38 criminal. If you know Lazarus at all you know that's somewhat complicated (#understatement), but my view of it is in this article, in this case I’d argue they’re acting primarily in a criminal capacity (IE for financial gain rather than conducting espionage).

How about clusters where different people use different marketing terms for the same adversary? I’m still working on that. To be honest, in most cases I trust clusters when I develop them, not when someone hands me a list. In cases like that I typically pick my own name and apply that broadly, but usually, I don’t. I just look at clusters. I’d rather find the overlaps myself. If Dragos, CrowdStrike, and SecureWorks all put out articles about APT groups at the same time, I’d probably add them something like this:

* `[ media:news=(Dragos Article,) +#adversary.attack.electrum ]`
* `[ media:news=(CrowdStrike Article,) +#adversary.attack.voodoobear ]`
* `[ media:news=(SecureWorks Article,) +#adversary.attack.ironviking ]`

Now, these aren’t clustered at all. Honestly, that’s okay. Associations can be made other ways that likely make more sense, such as overlaps of indicators or even just referencing other `media:news` articles that do attribution themselves.

```plaintext
[ media:news=(https://attack.mitre.org/groups/G0034/,) :url=https://attack.mitre.org/groups/G0034/ +#adversary.attack.electrum +#adversary.attack.voodoobear +#adversary.attack.ironviking ]
```		

Now what if you want a cluster and you really want to directly associate these. In a case like that, remember: tags are nodes too!

* `[ syn:tag=adversary.attack.electrum +#adversary.superbad_squad ]`
* `[ syn:tag=adversary.attack.voodoobear +#adversary.attack. superbad_squad ]`
* `[ syn:tag=adversary.attack.ironviking +#adversary.attack. superbad_squad ]`

Now these cat just be referred to using `storm #adversary.attack.my_meta_name -> syn:tag -> media:news`! Even better, if you trust the association enough, you could just build a trigger to persist this, so every time something gets tagged with a specific tag Synapse automatically adds the meta tag as well: `trigger add tag:add #adversary.attack.electrum {[ +#adversary.attack.superbad_squad ]}`.

Typically, `#adversary` tags are applied to `media:news` and other big concept reference things, sometime IOCs. Often this will happen after exploiting a news article, pulling the related IOCs, and using something like `[ media:news=(Dragos Article,) -(*)> * {[ +#adversary.attack.electrum ]} ]`.

Now where does my approach fall down? Every approach has some drawbacks, and mine, as you might have guessed, falls down when two analysts call two different groups the same thing. In my defense, that’s always confusing, but it’s the part you have to watch out with. This isn’t always bad, sometimes you want to know people get it wrong, and you can avoid other people's mistakes with your own meta cluster tags.

There are other, in many ways better) ways to do the same thing. You could consider threat groups an `ou:org`, either because they’re an organized group or because they’re (in some cases) an actual commercial or government entity. Ultimately, to follow the data model, you probably should also use the new(ish) `risk:threat` group. In fact, I’ve started using them for my more developed actors (many of whom already have `ou:org`s as well). So why keep using tags? Well, for one cutting over is still a WIP, but secondly because I can just use something like:

`trigger.add tag:add --tag adversary.espionage.apt28 --query { [ +(refs)> { risk:threat:name="APT28" } ] }`

If you’re not a trigger guru (I wasn’t until semi-recently) this will basically take anything I tag with `#adversary.espionage.apt28` and create a light edge named `refs` to the `risk:threat` I created for APT28. Now when I tag, which is my natural move, I get the more developed connection to my APT28 node as well! Automation gives us the best of both worlds!

## #️⃣ Infrastructure

> “The infrastructure feature describes the physical and/or logical communication structures the adversary uses to deliver a capability, maintain control of capabilities (e.g., command- and-control/C2), and effect results from the victim (e.g., exfiltrate data).” — [The Diamond Model of Intrusion Analysis](https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf)

Okay, wow, take a breath. I warned you adversaries would be a lot, and they were, but from here it’s straightforward (at least until the victim side of things because that’s basically attribution in reverse and comes with most of the same problems). Often I use Infrastructure tags to describe related IOCs, especially for network infrastructure.

To be fair, I’m still getting started:

```plaintext
cli> storm syn:tag^=infrastructure
Executing query at 2023/01/19 12:54:39.503
syn:tag=infrastructure
		.created = 2020/12/29 21:48:36.786
		:base = infrastructure
		:depth = 0
syn:tag=infrastructure.hoppoint
		.created = 2020/12/29 21:48:36.786
		:base = hoppoint
		:depth = 1
		:up = infrastructure
syn:tag=infrastructure.hoppoint.likely
		.created = 2020/12/29 21:48:36.786
		:base = likely
		:depth = 2
		:up = infrastructure.hoppoint
syn:tag=infrastructure.unknown
		.created = 2020/12/29 22:01:25.131
		:base = unknown
		:depth = 1
		:up = infrastructure
```

There are a few more I could think of right off the bat:

* `infrastructure.initialaccess.driveby`
* `infrastructure.initialaccess.phishing`
* `infrastructure.commandandcontrol.webservice`

You might recognize a few of those tags, and yes, they’re largely pulled from MITRE ATT&CK. Now [Synapse has a power-up to help](https://vertex.link/blogs/synapse-power-ups/), but I’m using this manually. It works for me, and I appreciate the readability.

## #️⃣ Capability

> ”The capability feature describes the tools and/or techniques of the adversary used in the event.” — [The Diamond Model of Intrusion Analysis](https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf)

Let's get down to it!

```plaintext
cli> storm --hide-props syn:tag^=capability
Executing query at 2023/01/19 13:01:07.967
syn:tag=capability
syn:tag=capability.exploit
syn:tag=capability.exploit.zeroday
...
syn:tag=capability.malware
syn:tag=capability.malware.macos
syn:tag=capability.malware.macos.dazzlespy
...
syn:tag=capability.malware.windows
syn:tag=capability.malware.windows.conti
syn:tag=capability.malware.windows.cyclopsblink
...
syn:tag=capability.weaponization
syn:tag=capability.weaponization.excel
```

Nothing too eventful here, at least I hope not!

* `exploits`: Just what you’d think. References to initial access code.
  * `exploits.zeroday`: Specifically calling out references to exploits that came out before a vulnerability.
* `malware`: Just what you’d think, general malware.
  * `malware.macos`: Targeting the Apple macOS
  * `malware.windows`: Targeting the Microsoft Windows
  * `malware.linux`: Not shown, but it’s there, same thing.
* `weaponization`: This is based on tools being used as a part of delivery
  * `weaponization.excel`: I think this one was referencing an exploit being delivered via an Excel macro.
  
I’m sure there could be more. Since I started writing, there are more! But none that are too inventive or insightful.

## #️⃣ Victim

> “A victim is the target of the adversary and against whom vulnerabilities and exposures are exploited and capabilities used.” — [The Diamond Model of Intrusion Analysis](https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf)

While we usually think of attribution in terms of adversaries it turns out, there’s another, less commonly used, kind of attribution: victims. I like tracking victims as much as I can because in a _**circumstantial way**_ it speaks to the adversaries intent (no not always, you’ve got to be careful with this). This is especially true if you can see an adversaries actions towards multiple victims over multiple campaigns.

```plaintext
cli> storm --hide-props syn:tag^=victim
Executing query at 2023/01/19 13:08:26.320
syn:tag=victim
syn:tag=victim.activist
syn:tag=victim.commercial
syn:tag=victim.commercial.\<COMPANY\>
...
syn:tag=victim.commercial.\<COMPANY>.\<SUBSIDIARY>
syn:tag=victim.government
syn:tag=victim.government.\<ISO3361 ALPHA2\>
...
syn:tag=victim.government.\<ISO3361 ALPHA2\>.\<AGENCY\>
syn:tag=victim.industry
syn:tag=victim.industry.cryptocurrency
...
syn:tag=victim.triton
```

Most of these are in the form of `#victim.<CLASS OF ENTITY>` such as activists, commercial entities, government entities, and industries (I differentiate these as attacking either unspecified or multiple victims). In many ways, these are my least developed set of tags, largely because they’re the least commonly found type of data. I respect the need to protect the companies involved, but I wish this sort of information was shared more. We certainly should be past the idea that getting breached is a rarity.

## Secondary Base Tags

In addition to the _Diamond Model_ tags, I also have a few others I use, somewhat arbitrarily, but I find them helpful. Most of these are not assessment tags, but extra metadata.

### #️⃣ Workflow

I use workflow tags to keep track of my own effort. These are pretty minor, a lot of them are focused on things like `workflow.next` (for stuff I want to focus on soon), `workflow.toexploit` (for resources I need to dig into further), and even `workflow.shortcuts` for resources I added via automation in [Siri Shortcuts](https://support.apple.com/guide/shortcuts/welcome/ios). Basically, these are tags to help me work better.

### #️⃣ Investigation/Project

I use these to manage comprehensive analysis projects. Usually, they’re named simply and concretely. So if I was investigating SMS Phishing attacks (which I am… and I’m annoyed as crap I keep getting those stupid SMS Phishes all the time) I’d create a tag like `#investigation.sms_phishing`.

### #️⃣ Nexus

Nexus is simple, it just lets me call out a related country or region, especially for stuff that’s more geopolitical than cyber. Typically, it’s just an [ISO-3361 alpha2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) two-letter country code, such as `nexus.ua` (🇺🇦❤️), similar to how I do victims.  It’s an imperfect but often useful set of tags.

### #️⃣ Keyword

These are most frequently created by automated systems to capture their outputs. This is useful for things like [VirusTotal tags](https://www.virustotal.com/gui/file/30c9df66a09dbd9c62468b35f0f0a40bb2d082490542edaed66b9c3bd10b0eda) for this Turla sample:

* `syn:tag=keyword.direct-cpu-clock-access`
* `syn:tag=keyword.peexe`
* `syn:tag=keyword.runtime-modules`

I don’t love this honestly, it probably needs another level of depth, but it’s functional so far. Many systems automate tags for a variety of things, and as long as the system generating the tags is somewhat consistent, you can see a lot of value. It’s always an evolution!

## In Closing

The fact you’re tagging data in Synapse is already a win, and there’s not really a right way to tag data most effectively. One of the great things about Synapse is while it’s opinionated in many ways, this is balanced with flexibility to allow you to add your workflows into Synapse. So think less about the _right way_ for everyone and think more about the _right way_ to tag & categorized data for your team. Will you get it right the first time? Maybe, maybe not. But you’ll get better at it over time, and that’s what matters.

Until you get it right remember two things: `movetag` is your friend and when in doubt believe!

{{< giphy DEZA7FlHbMesUF1jm9 >}}

### Bonus: ACTORS Model

[Paul Jaramillo](https://twitter.com/dfir_janitor) released a small, under the radar talk from a few years ago, dropped the excellent [ACTORS model](https://www.slideshare.net/PalJaramillo/bsides-chicago2017) for looking at adversary sophistication. Paul laid out the following characteristics to evaluate on a scale from 1-10:

* **Attack Precision:** Ability of Threat Actor to closely align their planned attacks with an organization's given vulnerabilities, including overall efficency.
* **Cross-platform Capabilities:** Ability of Threat Actor to operate in a full spectrum of diverse technologies.
* **Targeting:** Ability of Threat Actor to successfully compromise well-defended "hard" targets, as compared to "soft" targets.
* **Operational Security:** Ability of Threat Actor to avoid providing their adversaraies with any useful information about them.
* **Resilience:** Ability of a Threat Actor to maintain access in an organization's environment.
* **Stealth:** Ability of a threat actor to avoid detection.

My next goal is to implement this for some of the actors I keep tracking. It seems like it could be super easy (using his examples from the presentation):

```plaintext
cli> storm syn:tag=adversary.criminal.carbanak
Executing query at 2022/05/16 18:32:14.733
syn:tag=adversary.criminal.carbanak
		.created = 2022/05/16 18:32:05.330
		:base = carbanak
		:depth = 2
		:up = adversary.criminal
		#actors.attack_precision.10
		#actors.cross_platform_capability.7
		#actors.opsec.4
		#actors.resilience.4
		#actors.stealth.4
		#actors.targeting.4
complete. 1 nodes in 34 ms (29/sec).
```
  
Synapse reorders these out of acronym order, but the point is still there. This is a great way to track even more detailed characteristics of an adversary, and makes comparison possible. Either way, super useful information!
