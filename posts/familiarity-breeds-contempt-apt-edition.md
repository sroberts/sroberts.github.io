---
title: "Familiarity Breeds Contempt: APT\_Edition"
date: 2017-08-04T07:33:39.597Z
tags:
  - intelligence
  - network-defense
---

Here’s a familiar scenario:

> A new threat is being whispered about. Maybe your office has someone with special access of some kind and they’re being a bit more secret squirrely than usual. The mailing lists you’re on are a buzz about a new piece of malware or vendor code name. You keep hearing about a paid only report that tells all. _APT 46: EMPEROR PENGUIN_ is coming! When your boss asks about EMPEROR PENGUIN you have to say you don’t know much… but you’ve heard they’re very good, very advanced, well funded, with great opsec… obviously a serious threat aimed at hard targets (which your organization obviously is). More data starts trickling out. A blog post here and a malware report there. Someone you _know_ on Twitter or a mailing list is sharing their experience fighting off EP infections and then a PR post disclosing an EP breach, discussing how advanced and effective they were, bragging about the high end consultant team necessary to fight them off.

3(ish) months and a security conference later...

> Oh good you think to yourself, another lame vendor report about EMPEROR PENGUIN. You read the first two or three (That one from the one AV vendor was especially good) but EP is kinda lame now. Sure you have the “FEAR THE PENGUIN!” t-shirt you got at that conference but you’re not really concerned about EMPEROR PENGUIN. They don’t even attack your sector and even if they did they’re just a bunch of noobs: they have terrible opsec, their “malware” is just a bunch of Powershell scripts, and they reuse infrastructure all the time. Yeah, they’ve breached some stuff, but they’d never get into your network. Not even worth thinking about. Just some [skiddies](https://www.urbandictionary.com/define.php?term=skiddie).

This cycle happens all the time including this week with [Sednit/Turla](https://theintercept.com/2017/08/02/white-house-says-russias-hackers-are-too-good-to-be-caught-but-nsa-partner-called-them-morons/) (The link is to the Intercept with leaked 🇨🇦 classified data, visit at your own risk). Let's explore it a bit.

![There can be no prestige without mystery, for familiarity breeds contempt. ~ Charles de Gaulle](https://izquotes.com/quotes-pictures/quote-there-can-be-no-prestige-without-mystery-for-familiarity-breeds-contempt-charles-de-gaulle-69207.jpg)

Source: [izquotes.com](https://izquotes.com/quotes-pictures/quote-there-can-be-no-prestige-without-mystery-for-familiarity-breeds-contempt-charles-de-gaulle-69207.jpg)

### The Advanced Persistent Threat Hype Cycle

If you’ve been around the incident response/threat intelligence world long enough you’ve no doubt experienced this cycle for yourself. Here’s the breakdown:

- **Phase 0— Unknown:** The phase attackers would love to stay in forever when no one has even heard of them. This is largely during their preparation phase and initial stages of their campaigns, before the victims have noticed anything.
- **Phase 1— Mystery:** This is immediately after the adversary has been detected by a few lucky, skilled, or connected victims. They’re only actually known to those who worked the investigations and maybe mentioned to third parties but without generally available technical details. People know something happened, but very little about what happened, and the responders who actually do know are still being tight lipped. Depending on details and the opinions of the responders the view of the adversary may range from extreme concern to minimal worry.
- **Phase 2 — Awareness:** The real secret squirrel phase this is where the mailing lists and Slack channels start talking and sharing information. At this point the information starts to both expand (as context is added) and corrupted (as people make incorrect correlations). New investigations start, new compromises are discovered. Victims start sharing how advanced the adversary is. Generally speaking the adversary is considered pretty scary at this stage, as details are still being sussed out and people always assume the worst.
- **Phase 3 — Publicity:** The first blog posts start coming out, either by victim organizations or vendors (often vendors on victims “behalf”). The first real technical details emerge. Victims and vendors tell horror stories, either to assuage guilt over compromises (for the victims) or sell more of their solution (for the vendors). Companies & organizations who weren’t aware during Phase 3 quickly try to become aware. If they’re vendors they release follow on reports, based on real or imagined insights in their data. Adversary esteem is at an all time high.
- **Phase 4 — Condescension:** At some point though publicity curdles like spoiled milk. Maybe it’s too many vendors, too many t-shirts, victim false positives, it’s hard to say exactly but the mood changes. Rather than focusing on the advanced traits of the adversary the outsiders, generally those who became aware during the publicity phase, start focusing on all the reasons the adversary is… well… _bad at being an adversary_. They focus on shortcomings in capability, infrastructure, and operational security. Respect for the adversary, rising slowly but continuously during phases 1–3, suddenly starts declining and craters.
- **Phase 5 — Respect:** Here’s the rub. After getting called out adversaries take a few different tactics: go to ground and hide temporarily, change TTPs, go to ground for good, or accelerate their operation timeframe. If it’s the two former options (go to ground or change) then in many cases the adversary regains much of their lost respect, seen as a long term adversary and thus . If it’s the latter two approaches then the adversary respect stays low, viewed as lucky for the things they did right and derided for mistakes they made.

Overall and in short General de Gaulle’s quote holds true: **Mystery breeds prestige. Familiarity breeds contempt.**

Here is the APT Hype Cycle in picture form:

![APT Hype Cycle](/static/apt-hype-cycle.png "APT Hype Cycle")

[Original Graph](https://docs.google.com/spreadsheets/d/1QAPQdbKOlwp2RF5rdFAsnaKNIwV7f7cw_FzdRQNM-sI/edit?usp=sharing) based on the [Uncanny Valley](https://en.wikipedia.org/wiki/Uncanny_valley)

### Respecting Your Adversary

This graph leads us to two important concepts:

**Phase 3** is what I like to call **_The Peak of APT Superiority_**. The Peak is when defenders overestimate the skill, resources, and tradecraft of an adversary to the point that the defenders assume the adversary is nearly omnipotent. This is a dangerous attitude that leads to inaction due to paralysis in the face of an insurmountable foe where defenders are sure that a better resourced and more persistent foe will always beat their defenses. This peak was particularly pronounced after the [Kaspersky Equation Group report](https://securelist.com/files/2015/02/Equation_group_questions_and_answers.pdf) when compromise by NSA TAO was discussed not simply as a possibility but often as an inevitability.

**Phase 4** gives us what I’d like to call **_The Valley of Defender Condescension_**. The Valley of Condescension is equally as dangerous as the Peak, assuming that a once mysterious but now revealed foe is incapable and unworthy of effort. It leads to dismissiveness. Plenty of _unsophisticated (whatever that means)_ adversaries have compromised organizations and completed their goals. A prime example of this was the [Mandiant APT1 report](https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf), where many seem defenders seemed to forget just how effective the Unit 61398 had been against some very aware and well resourced victims.

_The fact is both the peak and the valley are elements of bias that as defenders we must avoid at all costs._ Overestimating and underestimating are both dangerous to our posture as defenders. The idea of threat intelligence is always about understanding the adversary. IOCs & TTPs are one thing but the idea of generalized adversarial capability, how scared we should be, is equally important and infinitely more abstract. Given that this “measure” is used to determine budgets and deploy resources we need to mitigate bias setting these levels.

The fact is adversaries are people just like defenders. They have budgets and bosses. Goals and metrics. Skills and habits. Just like defenders these things add up to an adversary’s strengths and weaknesses. Misunderstanding either aspect can be dangerous. **Instead we must seek to understand an adversary's strengths and weaknesses and eventually work to exploit their weaknesses and mitigate their strengths.** That’s a nice platitude, but can we actually do though?

- **Don’t buy into the hype!** A lot of folks will try to blame this sort of issue on vendors, but honestly everyone in security is culpable. We all peddle FUD when it suits us. Make sure you understand the information providers incentives and objectives. AV companies do great research, but they want to sell software. Consulting firms can share good information, but it’s to get you go call them next breach.
- **Gather your own information & generate your own intelligence.** Take the time to gather and evaluate data for yourself. Context always matters so unless a product is built for you it’s not intelligence to you, it’s just information.
- **Be realistic about your own threat model.** Worrying about the flavor of the month adversary should rarely be a thing. If you’re a hospital banking trojans aren’t worthy of much concern. Conversely malware aimed at medical devices shouldn’t scare the average bank.
- **Strive to be objective about the adversaries you need to focus on.** Gather your information, determine who you need to worry about, and generate your own intelligence focused on an objective, contextualized, and realistic understanding of the adversary.

In the end I couldn’t say it any better than Medal of Honor winner and Marine Corps Gunnery Sergeant John Basilone:

> "Never fear your enemy but always respect them." ~ _[John Basilone](https://en.wikipedia.org/wiki/John_Basilone)_
