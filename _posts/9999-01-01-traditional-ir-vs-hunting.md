---
layout: post
title: Incident Response is Dead...<br>Long Live Incident Response
---

Talk to anyone in the _DFIR Illumanati_ and one of the topics that always comes up is _hunting_. Much like threat intelligence & string theory people talk a lot about this, but nearly no one knows what it actually means.

![Amazing Meaningless Cyber Graphic](http://www.purdue.edu/apps/dpmanage/Resource/15627838ea7e43e4843415d5bb2d0303.jpg)

## Proactive vs. Reactive

At it's core _Hunting_ is about taking a proactive vs a reactive approach to incident. In _Reactive_ organizations an incident starts when notification comes in; whether that's an IDS or AV alert, or worse a phone call from the FBI or getting [Krebs](http://krebsonsecurity.com/)-ed. At that point an IR begins, reacting to the incoming event.

In _Hunting organizations_ the IR team actively goes looking for incidents based on known patterns of activity, intelligence, even just hunches. The major approaches are target centric (If we know Project Unicorn is valuable and possibly targeted, start hunting around people involved with Project Unicorn) or actor centric  (we know Actor Troll likes attacking organizations like ours, so identify as much information about Actor Troll and used that to proactively look across the organization)

## Hunting Mindset

What does it take to build a hunting team? First of all it takes a complete change in mindset and proceedures.

### A Target Centric Mindset

> <i class="fa fa-comments-o fa-2x pull-left"></i> know thyself ~ ancient greek proverb

### An Actor Centric Mindset

> <i class="fa fa-comments-o fa-2x pull-left"></i> Yes I know my enemies
They're the teachers who taught me to fight me
~ Know Thy Enemy by Rage Against the Machine

### Wide Ranging Telemetry

A good hunt team can use a basic indicator, like an IPv4Address, in multiple ways while hunting and in prevention. The more options a team has for getting telemetry the better their chances of identifying and collaborating malicious actions.

### Scalability & Automation

The tough thing about hunting is you're trying to prove a true negative. Put more simply: you're trying to prove their isn't something bad. What makes this tough _is the fact that it's impossible to prove a true negative._ You can never ultimately be sure you aren't digging deep enough.

The way to counter this is by hunting effeciently and widely. That requires a combination of scalability and automation.

### Management Buy In

Ok... this part gets weird. You would think that your leadership would be super excited to know about all these newly discovered incidents and having the chance to remediate them. Turns out they often aren't, especially if you work in a regulated industry (like finance, medicine, or the DIB). In many cases leadership would rather [_keep their head in the sand_](http://www.weedist.com/wp-content/uploads/2012/06/Head-In-Sand.jpg) than deal with the reality (like regulators), and the hunt team becomes a victim of it's own success. I know of one organization where a mature hunting team was told to [watch movies](http://www.imdb.com/title/tt1190536/) and [play video games](http://www.hedgewars.org/) rather than track down more malicious activity. #truestory

### Battle Rhythm

The _victim of their own success_ incident response team problems aren't limited to leadership. Once a hunt team begins to mature their ability to constantly find new malicious activity continues to improve until the point where they can basically find new malcious activity at will. As a result the IR team is basically in a constant state of emergency, always responding to something.

At this point the hunt team lead needs to step in and develop a mature "battle rhythm" to keep the team sane. While in reactive organizations treating every incident as an all hands on deck emergency makes sense this can't be the reality of .

### Incident Response

The Hunting vs Non-Hunting process is only relevent to the Preparation & Detection phases of an incident. Good hunting is useless unless your team can execute on the mitigation, remediation, and recovery phases effectively. Without that all you have is a larger incident load to fail to respond to.

## Hunting Tools

### Endpoint Interrogation Tools
- GRR

### Massive Logging
- ELK

## So what's the big deal?
