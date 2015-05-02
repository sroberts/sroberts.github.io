---
published: false
---

---
layout: post
title: Imposter Syndrome in DFIR
---

> Impostor syndrome can be defined as a collection of feelings of inadequacy that persist even in face of information that indicates that the opposite is true. It is experienced internally as chronic self-doubt, and feelings of intellectual fraudulence. 

[_Imposter Syndrome_ ~ The CalTech Consuling Center](https://counseling.caltech.edu/general/InfoandResources/Impostor)

There isn't really an easy way to jump into a post like like this and in many ways there doesn't need to be. Imposter Syndrome is something many people don't know a lot about (I'd never heard the idea until I started working at [GitHub](https://github.com/)) but it's something I think everyone is intimately familiar with. 

Imposter Syndrome is a lot like a childs boogie man; open the closet, turn on the lights, take a look around, and you see that nothing is there. For a moment you feel better. Exposing it, taking a good hard look, and acknowledging it makes a big difference. But it doesnt't go away entirely, it's temporarily gone, and eventually you'll have to expose it again. 

One of the complications with Imposter Syndrome is while everyone experiences imposter syndrome it manifests itself in unique and individualized ways. So with that in mind, and knowing that openness and honesty are the these keys (both to help myself and others), this is my take on the symptoms of imposter syndrome I have experienced as a Digital Forensics & Incident Response professional:

## The "Blinky Lights" Inferiority
> "What if they make a box that does what I do?"

When I was first getting into security as a Security Intern at [The Hershey Company](https://www.thehersheycompany.com/) I remember reading an article the upcoming Windows XP SP2 release focused on all of the security advancements (a built in firewall, [DEP](http://en.wikipedia.org/wiki/Data_Execution_Prevention), Security Center, etc). I still think of that release as the first "Security Release" from a major vendor; it wasn't but this was a formitive time for me, and it was a huge deal. 

My first thought was simple: _"I may as well give up on security, they're just going to make hacking impossible with this release."_

I was wrong (_oh so wrong_) and nieve, but in many ways this fear has never gone away. I thought the same thing for an instant when I first saw a beta [FireEye](https://www.fireeye.com/) appliance. What about when they fix _all_ the bugs? What if someone builds a box that does what I do?  What if machine learning actually becomes a real thing and it's better than I am?

The reality is much different. Maybe some day someone will build a box that does what I do but that's not today. This is the easiest Inferiority to look at and dismiss as silly, but that doesn't make is less potent from time to time.

## The Offensive Inferiority
> "Red team bros just constantly say how easy it is to get around what I spent months building."

There's a joke I love that goes like this (with my own small modification): 

> How do you tell if someone is a vegan, a crossfitter, or pentester? Give them two minutes and they'll tell you.

If you ever sit around with a bunch of offensive types (pentesters, vulneraiblity researchers, exploit developers) you'll quickly start hearing stories that can basically get boiled down to "Defense is garbage, defenders are useless, we always win, I'm super awesome." It'll rarely be said that way directly of course but as a defensive type with a group of offensive types it quckly starts to feel like you're just directly being called an idiot.

Now I have plenty of friends who are offensive security professionals (as well as friends that are vegans and crossfitters) and this isn't really their fault. We all tell war stories in a way that focuses on our successes rather than our failures. What can be tough is you never hear a pentester talk about the time they failed for a week straight to achieve a target, you only hear about the epic success when they got in. You never here a vulnerability researcher describe the weeks in IDA getting frustrated, only the feeling when they finally launched their exploit and saw calc.exe pop up.

The fact is a defensive team can succeed 999 out of 1000 times, and the only thing anyone cares about is the 1 in 1000 where they failed. In the same way offensive teams never dicuss the 999 times they failed, only the last time when they finally succeed. This leads to DFIR folks often feeling like their job is in vain but I would argue the opposite, we succeed often, we just rarely acknowledge it.

## The "Jack of All Trades" Inferiority
> "I'm a worse RE than our RE and a worse 4n6 than our 4n6icator and a worse dev then our developer and a worse ops than our ops."

Going from the team perspective to an individual contributor perspective I fidn DFIR folks have an easy time getting down on themselves. A DFIR/Incident Handler  is often a leader or contributor to a team of specialists. In times where I've worked as a primary incident handler my job was to ingest information coming from the specalists, synthasize it into a plan, and execute that plan. 

I'm a terrible malware reverser reliant mostly on tools like Yara and Cuckoo Sandbox (and if I'm honest VirusTotal), but I know enough to read a strong reversers report and understand it. My skills in EnCase are limited to basic triage, but I know enough to help out in the beginning of an investigation and make use of my dedicated forensics engineers output. In these cases my real strength is the fact that I understand everyones job enough, and know how to fit it into the bigger picture. This means my team's reverser doesn't have to worry about forensics and vice versa. 

But it's tough to feel that everyone is more skilled, even if it's only in their personal area of expertiese. I'm not as good at reversing as a RE, but I'm much better at reversing than most foreniscs engineers, and I know more about intelligence too. It's a unique set of skills to see the big picture.

## The "80/20" Inferiority
> "About 95% of the time I just sit around being a mediocre software developer or systems engineer."

I deliberately structured this post in what, for me, is the order of my imposter syndrome issues. I'm less concerned that RSA is going to release a "SRoberts Replacement Box":tm: than I am frustrated by "Pentester Bros" bragging about their conquests (and ignoring their defeats). The toughest for me to deal with though is this: 90% of the time I feel useless. 

When I interviewed for my position with GitHub I told my future employeer's CEO "...the best thing for the company would be for me to be bored all time time". It was meant to be a little cheeky, but it's honest; when you see accountants, lawyers, or incident handlers stressed out and frazzled it's going to be a rough few weeks.

No organizations are without incidents but the fact is while there's always something to do there are also "non-emergency times" (in varying ratios) where as an incident handler it's easy to feel like a 3rd wheel. I spend a lot of that time building new systems, either as an ops person or a developer. This ties back to the _Jack of All Trades_ issue, but I know I'm not nearly as good a developer as our real developers. Nor am I as good an ops engineer as our real ops engineers. It's easy to feel somewhat anncilary, at least until the next emergency. 

## The "Human Being" Inferiority

At it's core all of these issues tie back to one issue; being human. The only convievable way to 100% avoid ever feeling the symptoms of imposter syndrome is to avoid self analysis entirely. It's unavoidable, but simply knowing others experience the same thing is freeing. I remember reading a friend, a brilliant, skilled friend that no one would ever expect to feel like an imposter, writing a brutally honest account of feeling like they were going to be discovered as a fraud. It was a moment of pure humility on their part and ended up being a moment of pure empathy on mine. This person I respected, always found insightful, never seemed to say "I don't know", had the same insecurities I did?

## In The End

It was in the vain of that friend that I chose to write this. I admit I often don't feel like I'm prepared to be a part of this profession I've chosen. I feel like I should know more, read more, write more, code more, and generally be a whole lot better at RE, forensics, coding, intelligence analysis, OSINT gathering, etc. And I'm pretty sure all that is normal. 

No one ever gets away from Imposter Syndrome entirely. It's a human condition, but we can seek to understand it, to control it, and not let it control us. I think a willingess to confront this, withourselves and our teams, can make everyone stronger.