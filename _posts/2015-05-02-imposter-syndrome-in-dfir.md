---
layout: post
title: Imposter Syndrome in DFIR
---

> Impostor syndrome can be defined as a collection of feelings of inadequacy that persist even in face of information that indicates that the opposite is true. It is experienced internally as chronic self-doubt, and feelings of intellectual fraudulence.

[_Imposter Syndrome_ ~ The CalTech Counseling Center](https://counseling.caltech.edu/general/InfoandResources/Impostor)

There isn't an easy way to jump into a post like this and in many ways there doesn't need to be. Imposter Syndrome is something many people don't know a lot about (I'd never heard the idea until I started working at [GitHub](https://github.com/)) but it's something I think everyone is intimately familiar with.

![Which one is the boogie man?](https://38.media.tumblr.com/tumblr_m8txuocJ481rqten0o1_500.gif)

Imposter Syndrome is a lot like a child's boogie man; open the closet, turn on the lights, take a look around, and you see that nothing is there. For a moment you feel better. Exposing it, taking a good hard look, and considering the logic it makes a difference. But it doesn't go away entirely, it's temporarily gone, and you'll have to expose it again.

One of the complications with Imposter Syndrome is while everyone experiences imposter syndrome it manifests itself in unique and individualized ways. So with that in mind, and knowing that openness and honesty are the these keys (both to help myself and others), this is my take on the symptoms of imposter syndrome I have experienced as a Digital Forensics & Incident Response professional:

## The "Blinky Lights" Inferiority
> <i class="fa fa-comments-o fa-3x pull-left"></i> "What if they make a box that does what I do? Like the Terminator but for SOC work."

When I was first getting into security as a Security Intern at [The Hershey Company](https://www.thehersheycompany.com/) I remember reading an article the upcoming Windows XP SP2 release focused on the upcoming security advancements (a built in firewall, [DEP](http://en.wikipedia.org/wiki/Data_Execution_Prevention), Security Center, etc). I still think of that release as the first "Security Release" from a major vendor; it wasn't but this was a formative time for me, and it was a huge deal.

![A Blink Light Box](http://www.plinkusa.net/products/G2220S-16.gif)

My first thought was simple: _"I may as well give up on security, they're just going to make hacking impossible with this release."_

I was wrong (_oh so wrong_) and naive but in many ways this fear has never gone away. I thought the same thing for an instant when I first saw a beta [FireEye](https://www.fireeye.com/) appliance. What about when they fix _all_ the bugs? What if someone builds a box that does what I do?  What if machine learning actually becomes a real thing and it's better than I am?

The reality is much different. Maybe some day someone will build a box that does what I do but it won't be today and tomorrow isn't looking promising either. This is the easiest Inferiority to look at and dismiss as silly, but that doesn't make is less potent from time to time.

## The Offensive Inferiority
> <i class="fa fa-comments-o fa-3x pull-left"></i> "Red team bros just constantly say how easy it is to get around what I spent months building."

There's a [joke](https://uproxx.files.wordpress.com/2015/01/archer-burn.gif?w=650) I love that goes like this (with my own small modification):

> How do you tell if someone is a vegan, a crossfitter, or _red team bro_? Give them two minutes and they'll tell you.

If you ever sit around with a bunch of offensive types (pentesters, vulnerability researchers, exploit developers, etc) you'll start hearing stories that can basically get boiled down to "Defense is garbage, defenders are useless, we always win, I'm super awesome." It'll rarely be said that way (and if it is get new friends) but as a defensive focused person it starts to feel like you're just directly being called an idiot.

![Hacker Bragging Origins](http://38.media.tumblr.com/25381459d5898e2daf10b16c59d66955/tumblr_nl4nqvsTUK1s49n8po1_500.gif)

Now I have friends who are offensive security professionals (as well as friends who are vegans and [crossfitters](https://www.youtube.com/watch?v=pqb9pBJweVU)) and this isn't their fault. We all tell war stories in a way that focuses on our successes rather than our failures. What can be tough is you never hear a pentester talk about the time they failed for a week straight to achieve a target, you hear about the epic success when they got in. You never here a vulnerability researcher describe the weeks in IDA getting frustrated, only the feeling when they finally [launched their exploit and saw calc.exe pop up](http://2.bp.blogspot.com/-6DX89aYwS7Y/UJBl7YXEL1I/AAAAAAAAABo/mm0VnPGZELY/s1600/timeout.gif).

A defensive team can succeed 999 out of 1000 times and the only thing anyone cares about is the 1 in 1000 where they failed. In the same way offensive teams never discuss the 999 times they failed, only the final time when they succeed. This leads to DFIR folks often feeling like their job is in vain but I would argue the opposite, we succeed often, we just rarely acknowledge it.

## The "Jack of All Trades" Inferiority
> <i class="fa fa-comments-o fa-3x pull-left"></i> "I'm a worse RE than our RE and a worse 4n6 than our 4n6icator and a worse dev then our developer and a worse ops than our ops."

Going from the team perspective to an individual contributor perspective I find DFIR  folks have an easy time getting down on themselves. Incident Handlers are not the usual [_T-Shaped People_](http://web.archive.org/web/20110329003842/http://www.chiefexecutive.net/ME2/dirmod.asp?sid=&nm=&type=Publishing&mod=Publications::Article&mid=8F3A7027421841978F18BE895F87F791&tier=4&id=F42A23CB49174C5E9426C43CB0A0BC46). While most people have one skill they're a 8 of 10 on and lots of skills they're a 3 of 10 in most DFIR types are a 5 out of 10 in four or fives skills and a 3s on the rest.

I'm not a great malware reverser, I rely on tools like [Yara](http://plusvic.github.io/yara/) or [Cuckoo Sandbox](http://www.cuckoosandbox.org/) and seldom break out Hopper, but I know enough to read an in-depth malware report and understand it. I have limited skill with EnCase but I know enough to do triage and make use of my dedicated forensics engineers output. In these cases my real strength is the fact I understand everyone's job enough, and know how to fit it into the bigger picture. This means the team's reverser doesn't have to worry about forensics and vice versa.

But it's tough to feel that everyone is more skilled, even if it's their area of expertise. I'm not as good at working with malware as a RE, but I'm much better at reversing than most forensics engineers, and I know more about intelligence too. It's a unique set of skills to see the big picture that has a unique and important place on a team.

## The "80/20" Inferiority
> <i class="fa fa-comments-o fa-3x pull-left"></i> "About 95% of the time I just sit around being a mediocre software developer or systems engineer."

I structured this post in what for me is the order of my imposter syndrome issues. I'm less concerned that RSA is going to release a "SRoberts Replacement Box":TM: than the "Pentester Bros" frustrate me by bragging about their conquests (and ignoring their defeats). The toughest for me to deal with though is this: 80% of the time I feel useless. DFIR types live for emergencies, but the fact is there just isn't always an emergency.

![80/20 Rule](https://lh6.googleusercontent.com/xB3fRshdfQvPqWYeUbBnCfrl6VnHycVp2XIvCOe4rpfKGTmyYwq-rsT_yMWjdqxudMJufQT5Ur3KRO4Ud8fyLTXwQXb-IQgXrae6PcmRxtogBRpjzqs)

No organizations are without incidents but the fact is while there's always something to do there are also _non-emergency_ times where as an incident handler it's easy to feel like a 3rd wheel. I spend a lot of that time building new systems, either as an ops engineer or a developer. This ties back to the _Jack of All Trades_ issue, but I know I'm not nearly as good a developer as our real developers. Nor am I as good an ops engineer as our real ops engineers. It's easy to feel somewhat ancillary, at least until the next emergency.

## The "Human Being" Inferiority

![Emotions!](http://img.photobucket.com/albums/v131/divalicious04/GIFs/myemotions_troy.gif)

At it's core these aspects tie back to one main issue; being human. The only conceivable way to 100% avoid ever feeling the symptoms of imposter syndrome is to avoid self analysis entirely. It's unavoidable, but simply knowing others experience the same thing is freeing.

I remember reading a post by a brilliant, noteworthy colleague that no one would ever expect to feel like an imposter, writing a brutally honest account of feeling like others were going to find out the poster was a fraud. The text was a moment of pure humility on the author's part and ended up being a moment of pure empathy on mine. This person I respected, always found insightful, never seemed to need to say "I don't know", had the same insecurities I did? That post gave me confidence, if only in knowing I wasn't alone.

## In The End

In the vain of that friend that I chose to write this. I admit I often don't feel like I'm prepared to be a part of this profession I've chosen. I feel like I should know more, read more, write more, code more, and generally be a whole lot better at RE, forensics, coding, intelligence analysis, OSINT gathering, etc. And I'm pretty sure all that is normal.

No one ever gets away from Imposter Syndrome entirely. It's a human condition, but we can seek to understand it, to control it, and not let it control us. I think a willingness to confront this, with ourselves and our teams, can make everyone stronger.
