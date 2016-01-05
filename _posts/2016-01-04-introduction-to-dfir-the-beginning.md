---
layout: post
title: Introduction to DFIR - The Beginning
---

One of my favorite things is talking to students and people new to the security field. It feels like yesterday I was wandering around the first [Shmoocon](http://shmoocon.org/) as a student in awe of the people I met and the work they were doing. Now I'm 10 years into my career and have a whole different perspective (though still in awe with those folks). Starting a career in infosec isn't easy and while [there are better general introductions](http://tisiphone.net/2015/10/12/starting-an-infosec-career-the-megamix-chapters-1-3/) I wanted to add my perspective on getting started in Digital Forensics and Incident Response (DFIR).

## What is DFIR anyway?

Digital Forensics & Incident Response is a multidisciplinary profession that focuses on identifying, investigating, and remeidating computer network exploitation. This can take varied forms and involves a wide variety of skills, kinds of attackers, an kinds of targets. We'll discuss those more below.

First though lets start with a core question: Do you want to do DFIR? You'll need the following traits (not all, but at least a majority of them):

- __Curiosity:__ It's always about what you don't know.
- __Attention to Detail:__ You never know what bit of data makes the difference.
- __A Need for Variety:__ One day it's logs, the next it's packets, then memory.
- __Working with People:__ There's always an attacker and a victim.
- __An Affinity for Stress:__ You don't have to like it, but you must handle it.
- __The Taste for Blood:__ Great DFIR engineers want to win and hate to lose.

Want to know more about what DFIR looks like? I recommend reading [The Cuckoo's Egg](http://www.amazon.com/The-Cuckoos-Egg-Tracking-Espionage/dp/1416507787/ref=pd_sim_14_17) by Clifford Stole. If that gets you excited journey on!

## This Series

DFIR, at least as I view it, is a broad field so here are some of the basic of the things you should know as an introduction to DFIR and where to learn more. Over the coming days I'm going to post about various topics in DFIR (more below) and people learn differently I will provide a few different types of resources. Each topic will have:

- __A video:__ For an easy broad introduction.
- __A link:__ To a site focused on that topic.
- __A tool:__ The _if you're going to know one tool this is the one_.
- __A book:__ To go deep into a subject you'll have a comprehensive resource.
- __A person:__ An expert in each subject who you'll want to learn from.

Lets get started.

## DFIR Skills

DFIR is a mix technical and soft (people & process) skills. DFIR is a skill unto itself we'll start with some general resources then get into specifics..

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Threat Analysis of Complex Attacks](https://www.youtube.com/watch?v=Yh1XZf0hLS4) | From SANS DFIR Summit in 2015. Shows the variety of skills across IR analyzing an interesting attack. |
| Link | [Journey into Incident Response](http://journeyintoir.blogspot.com/) | Corey is a veteran incident responder who shares tons of resources big and small on his blog. |
| Tool | [Redline](https://www.fireeye.com/services/freeware/redline.html) & [OSXCollector](http://yelp.github.io/osxcollector/) | Live response tools. Windows and OSX respectively. Try them out on your own systems. |
| Book | [Digital Forensics and Incident Response 3rd Edition](http://www.amazon.com/Incident-Response-Computer-Forensics-Edition/dp/0071798684) | The name is a give away, but it's a legitimately great book that covers the breath of IR. |
| Person | [@jackcr](https://www.twitter.com/jackcr) - Jack Crook | Jack's Twitter feed is a letter to new analysts. Easy things to learn and hard truths in the same breath. Every DIFR should read it. Honorable Mention to [@hacks4pancakes](https://twitter.com/hacks4pancakes). |

### Technical Skills

The first category of skills that I split DFIR into is technical skills. These are hands on keyboard skills focused on levels of an investigation.

- File System Forensics
- Memory Forensics
- Network Forensics
- Malware Triage
- Log Analysis
- Intelligence Analysis
- Development

### Soft Skills

I think soft skills get overlooked in the DFIR world. We focus so deeply on esoteric system minutia we don't realize we lack to the ability to make it relevant to others or in some cases even protect ourselves. These skills are important as they enable every one of the technical skills.

- Investigation Process & Analysis
- Operational Security
- Communication
- Working in a Team

## T Shaped People

That list above is a lot but it covers the broad set of skills DFIRs have. Is every DFIR a master of all these skills? Not at all (Ok, I know one guy who might be but he's total freak). Most DFIRs specialize in a few aspects and have less knowledge in others.

![T-Shaped People](https://docs.google.com/drawings/d/1c6xxt6JktO08HT6fIxEaCW50fVjHRvGnzbpECPMUmqk/pub?w=960&h=720)

This makes most DFIRS [_T-Shaped People_](https://en.wikipedia.org/wiki/T-shaped_skills) (see the T above now?), who have deep skills in specific areas and more limited in skills in others. [I've talked before](http://sroberts.github.io/2015/05/02/imposter-syndrome-in-dfir/#the-jack-of-all-trades-inferiority) about how I'm confident in some of my skills and less so in other skills. One of the things that makes DFIR different than many other professions is most DFIRs are jack of all trade types. I'm not excellent at malware analysis, but I can do a little bit. At the same time I'm better at Network Forensics than most.

Why is this important? Two key reasons:

- Not everyone needs to have the same skills. It's ok to have an affinity for a one skill and struggle a bit more with another.
- DFIR teams must focus on complimentary skills. If you have a team strong in memory forensics perhaps you want your next hire to be a strong malware analyst. No one person can be an expert in everything, but your team should have strength across the board.

## What's Next?

Originally I planned on making this one big post but too many people recommended too many great resources and things spiraled out of control. Instead I'm dividing this up into separate posts. First we'll start with the _technical skills_ then move on to _soft skills_ which are less technical, but still important (sometimes even more so). Just like the _DFIR Skills_ section above I'll have a video, link tool, book, and person for each.

Yeah... that's a lot. A post once a day for the next 10 business days. Hopefully it'll be a great set of resources for newbies and long time practitioners alike. No DFIR knows it all, so there's always a chance to learn.
