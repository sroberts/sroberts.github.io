---
layout: post
title: APT is a Who not a What... And Why it doesn't Matter
---

A small number of topics get intelligence driven incident responders incredibly frustrated:

- Using intelligence to mean smart (I'll share more about that later this week)
- Bad attribution based on incomplete information and bad assumptions
- Misuse of the term APT (in most cases by marketing departments)

Advanced Persistent Threat remains the buzzword of choice for vendors, but it's used incorrectly, and lots of people know that and don't say anything. As a result I want to go on the record and correct a couple key misnomers.

## APT is a Who

My second job after college was working for [Mandiant](https://www.mandiant.com/) as a Security Consultant. This was a great job where I learned a ton and that was because I worked with such a skilled team. The team that started Mandiant primarily came from the [United States Air Force Office of Special Investigations](http://www.osi.af.mil/); a team that handled, among other things, some of the first nation state level computer intrusions of the Internet era such as [Solar Sunrise](http://en.wikipedia.org/wiki/Ehud_Tenenbaum), [Moonlight Maze](http://en.wikipedia.org/wiki/Moonlight_Maze), and [Titan Rain](http://en.wikipedia.org/wiki/Titan_Rain).

This was a weird time, because (like today) attacks weren't just aimed at military targets but commercial targets as well. AFOSI, as well as other government intelligence & defense groups, investigated using open source and classified methods. For operational security, this leads to classified intelligence.

This classified intelligence was a problem. While the Defense Industrial Base has people with clearances who can handle classified data, other companies, without cleared people, came under attack as well. These DoD/IC teams wanted to help, but couldn't disclose classified information.  They came up with a compromise: __sharing indicators and information without disclosing the actual actor behind it. Instead they just referred to the actor using a pseudonym: The Advanced Persistent Threat.__ Specifically APT, supposedly coined by Colonel Greg Rattray, was a couple groups of actors primarily operating out of mainland China and believed to be members of the People's Liberation Army. We now know these groups today as _APT1_, _Anchor Panda_, and _Elderwood_, as well as other private designations.

__APT is a term to refer to Chinese espionage without saying Chinese espionage. Full stop.__

## APT is _not_ a What

Compromised companies often make a statement after their incident that the attacker is an _advanced persistent threat_. This leads to the same tired observations by security pundits:

> As our research team reveals in our Hacker Intelligence Initiative Report, some APTs are relatively simple to execute. ~ [Amichai Shulman](http://www.scmagazineuk.com/apts-not-as-advanced-as-you-might-think/article/345953/)

or...

> Advanced wasn't right because the initial gambit was almost always a low-tech spear phishing attack. Persistent wasn't really accurate because it wasn't the attackers who made things persistent; it was the inability of organizations to read their own logs for anomalies that allowed the breaches to continue over long timeframes. ~ [Robert Richardson](http://searchsecurity.techtarget.com/opinion/Advanced-persistent-threats-Has-the-industry-moved-on)

Robert is correct in this case. APTs aren't advanced or persistent, at least not necessarily. But that's because the term wasn't meant to describe _how_ the attacks occurred, but _who_ the attacker was. The APT term could have been "Actor Potato" or "Group1" or any other codename imaginable.

APT is not a description of an actor based on the sophistication of their techniques, as people often note there's often little that's advanced. They aren't universally persistent; while some groups will linger for months or years, others use _smash and grab_ tactics. __The fact is the same: APT is a codename for a who, that who being Chinese espionage, not a description of an attacker based on methods or techniques.__

## So why doesn't it matter?

This rant, and even I can call it a rant, isn't out of nowhere. Today Kaspersky released a report about the [_Carbanak APT_: A financially motivated attacker operating all over the world](http://securelist.com/blog/research/68732/the-great-bank-robbery-the-carbanak-apt/)(Report: [<i class="fa fa-file-pdf-o"></i> Carbanak_APT_eng.pdf](http://25zbkz3k00wn2tp5092n6di7b5k.wpengine.netdna-cdn.com/files/2015/02/Carbanak_APT_eng.pdf)). I have no doubt that this is a great paper worth reading. I have no doubt the group they describe is using some interesting, even advanced, techniques. Perhaps they even stay in an environment for a long period of time, persisting if you will. But I am 100% certain this is a misuse of the term APT.

__APT has moved away from its original definition, from a term of art to a term of marketing. It's not descriptive, except to say that the solution has to include hundreds of thousands of dollars in professional services, endpoint monitoring, intelligence portals, and feeds with millions of indicators.__ Words change, and there is no doubt at this point that APT _means_ what marketing says it does, but I think security practitioners can help.

We need a better and honest taxonomy for referring to these attackers. I'll kick things off with:

- State Sponsored Espionage (What we now call APT)
- Financially Motivated Criminals
- Nationalist Activists
- Criminal Activists (So called Hactivists)

Beyond just having a better taxonomy we need to work alongside marketing departments to use accurate, descriptive terms instead of overloaded buzzwords. It may be an uphill fight, but a worthwhile one. I welcome the chance to collaborate with others who care about this.

The security community has difficult problems on its hands. Seemingly the harder we work to stop threats the more come up. We're already dramatically understaffed as an industry ([<i class="fa fa-file-pdf-o"></i> Leviathan Security Group: Analysis of Cloud vs. Local Storage:
Capabilities, Opportunities, Challenges](http://www.leviathansecurity.com/wp-content/uploads/Value-of-Cloud-Security-Scarcity.pdf)). The last thing we need, the last thing we can afford, is to make our own lives more difficult by abusing overloaded terms to generate fear, uncertainty, and doubt.

## A Little Extra
I've been working on tool I think could be useful in situations like this. While it's not ready for prime time yet here is a little preview:

<script src="https://gist.github.com/sroberts/4a6677e66989d74a42ae.js"></script>
