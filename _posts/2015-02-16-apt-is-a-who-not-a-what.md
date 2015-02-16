---
layout: post
title: APT Is a Who, Not a What
---

A small number of topics that get intelligence driven incident responders frustrated:

- Using intelligence to mean smart (I'll share more about that later this week)
- Bad attribution based on incomplete information and bad assumptions
- Misuse of the term APT (in most cases by marketing departments)

Advanced Persisten Threat remains the buzzword of choice for vendors, but its used incorrectly, and lots of people know that and don't say anything. So I want to correct the key misnomer:

## APT is a Who

My second job was working for Mandiant as a Security Consultant. This was a great job where I learned a ton, and that was because I worked with such a skilled team. The team that started Mandiant primarily came from the Air Force Office of Special Investigations a team that handled, among other things, some of the earliest computer intrusions such as Solar Sunrise, [Moonlight Maze](http://en.wikipedia.org/wiki/Moonlight_Maze), and [Titan Rain](http://en.wikipedia.org/wiki/Titan_Rain).

This was a weird time, because like today attacks weren't just aimed at military targets but commercial targets as well. AFOSI, as well as other government intelligence & defense groups, were investigating using open source and classified methods. For operational security this leads to classified intelligence.

This was a problem. While companies in the Defense Industrial Base may have people with clearances who can handle classified data other types of companies, without cleared people who could handle that intelligence, were under attack as well. These DoD/IC teams wanted to share information, but couldn't disclose classified information.  They came up with a compromise: __Sharing indicators of compromise without disclosing the actual actor behind it. Instead they just referred to the actor using a pseudonym: The Advanced Persistent Threat.__ Specifically APT is a couple groups of actors primarily operating out of mainland China and believed to be members of the People's Liberation Army. We now know these groups as _APT1_, _Anchor Panda_, and _Elderwood_ as well as other private designations.

__That it: APT is a term to refer to Chinese espionage without saying Chinese espionage. Full stop.__

## APT is not a What

Compromised companies often make a statement after their incident that the attacker is an _advanced persistent threat_. This leads to the same tired sarcastic observations by security pundits:

> Advanced wasn't right because the initial gambit was almost always a low-tech spear phishing attack. Persistent wasn't really accurate because it wasn't the attackers who made things persistent; it was the inability of organizations to read their own logs for anomalies that allowed the breaches to continue over long timeframes. ~ [Robert Richardson](http://searchsecurity.techtarget.com/opinion/Advanced-persistent-threats-Has-the-industry-moved-on)

Robert is correct in this case. APTs aren't advanced or persistent, at least not necessarily. The APT term could have been "Actor Potato" or "Group1" or any other codename imaginable.

APT is not a description of an actor based on the sophistication of their techniques, as people often note there's often little about that that's advanced. They aren't universally persistent, some groups will linger for months, others uses _smash and grab_ tactics. __The fact is the same: APT is a codename for a who, that who being Chinese espionage, not a description of an attackers based on methods or techniques.__

## So what now?

This rant, and even I can call my own rant a rant, isn't out of nowhere. Today Kaspersky released a report about the [_Carbanak APT_: A finaically motivated attacker operating all over the world.](http://securelist.com/blog/research/68732/the-great-bank-robbery-the-carbanak-apt/) I have no doubt that this will be a great paper worth reading. I have no doubt the group they describe is using some interesting techniques. But I am 100% certain this is a misuse of the term APT.

__APT has moved away from its original defintion, from a term of art to a term of marketing. It's not descriptive, except to say that the solution has to include hundereds of thousands of dollars in professional services, endpoint monitoring, intelligence portals, and feeds with millions of indicators.__

We need a better set of taxonomy, an honest taxonomy, for referring to these attackers. I'll kick things off with:

- State Sponsored Espionage (What we now call APT)
- Finaically Motivated Criminals
- Nationalist Activist
- Criminal Activist (So called Hactivists)

The security community has difficult problems on it's hands. Seemingly the harder we work to stop threats the more come up. We're already dramatically under staffed as an industry ([Leviathan Security Group: Analysis of Cloud vs. Local Storage:
Capabilities, Opportunities, Challenges](http://www.leviathansecurity.com/wp-content/uploads/Value-of-Cloud-Security-Scarcity.pdf)). The last thing we need, the last thing we can afford, is to make our own lives more difficult by abusing overloaded terms to generate fear, uncertainty, and doubt.