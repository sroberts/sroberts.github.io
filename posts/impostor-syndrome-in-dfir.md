---
title: "Imposter Syndrome in\_DFIR"
date: 2015-05-02T04:00:00.000Z
tags:
  - network-defense
  - meta
---

> _Impostor syndrome can be defined as a collection of feelings of inadequacy that persist even in face of information that indicates that the opposite is true. It is experienced internally as chronic self-doubt, and feelings of intellectual fraudulence._

[_Imposter Syndrome_ ~ The CalTech Counseling Center](https://counseling.caltech.edu/general/InfoandResources/Impostor)

There isn’t an easy way to start a post like this and there doesn’t need to be. Imposter Syndrome is something most people don’t know a lot about (I’d never heard the idea until I started working at GitHub) but it’s something everyone is intimately familiar with.

![Boo!](https://miro.medium.com/max/500/0*UGJb4TwKRNmNX5dh.gif)

Imposter Syndrome is like the boogie man: open the closet, turn on the lights, look around, and you see that nothing is there. You feel better. Exposing it, taking a good hard look, and considering the thing is what nullifies it. But it never goes away entirely. It’s just temporarily gone, and you’ll have to expose it again.

While everyone experiences imposter syndrome, it manifests itself in unique and individualized ways. So with that in mind, and knowing that openness and honesty are the these keys (both to help myself and others), this is my take on the symptoms of imposter syndrome I have experienced as a Digital Forensics & Incident Response professional:

### The Technology Replacement Inferiority

> _“What if they make a box that does what I do? Like the Terminator but for SOC work.”_

Early in my career I read an article the then-upcoming Windows XP SP2 release and its focus on security (built-in firewall, [DEP/NX](http://en.wikipedia.org/wiki/Data_Execution_Prevention), Security Center, etc). This was a formative time in my career and this was a major advancement that I misunderstood entirely.

![sroberts replacement box](https://miro.medium.com/max/700/0*C6GiqMfWfoIAElk6.gif)

My first thought was simple: _“I may as well give up on security, they’re just going to make hacking impossible with this release.”_

I was naive and mistaken but this fear has never gone away completely. I thought the same thing years later when I first saw a [FireEye](https://www.fireeye.com/) appliance. What if they fix _all_ the bugs? What if someone builds a box that does what I do? What if machine learning actually becomes a real thing and it’s better than I am?

Reality is much different. **I sometimes feel like an imposter because someday someone will build a box that does what I do better than I can.** Someday won’t be today and tomorrow isn’t looking promising either. This is the easiest inferiority to look at and dismiss as silly, but that doesn’t make it less potent from time to time.

### The Offensive Inferiority

> _“Red team bros just constantly say how easy it is to get around what I spent months building.”_

There’s a [joke](https://uproxx.files.wordpress.com/2015/01/archer-burn.gif?w=650) I love that goes like this (with my own small modification):

> _How do you tell if someone is a vegan, a_ [_crossfitter_](https://www.youtube.com/watch?v=pqb9pBJweVU)_, or red teamer_? Give them two minutes and they’ll tell you.

Hang out with offensive types (pentesters, exploit developers, etc) and you’ll hear stories that can basically get boiled down to _“Defense is garbage, defenders are useless, we always win, I’m super awesome.”_ It’s never said that way (otherwise get new friends) but as a DFIR, this feels like being called an idiot all night.

![Hack & Burn!](https://miro.medium.com/max/500/1*iOVZi6dxKG24MqhuxVLWMw.gif)

**To be clear: This is my hang up.** This is not my offensive friends’ fault. We all tell stories focused on our successes, not our failures. It’s tough when you never hear a pentester talk about the time they failed for a week straight to compromise a target. Instead you hear about the epic success when they [got their shell](https://sroberts.github.io/public/equation.jpg). You never hear a vulnerability researcher describe the weeks in [IDA](https://www.hex-rays.com/products/ida/) (or [Vivisect](https://github.com/vivisect/vivisect)) getting frustrated. But you do hear about when they [launched their exploit and saw calc.exe pop up](http://2.bp.blogspot.com/-6DX89aYwS7Y/UJBl7YXEL1I/AAAAAAAAABo/mm0VnPGZELY/s1600/timeout.gif).

A defensive team can succeed 999 out of 1000 times and the thing everyone cares about is the 1 in 1000 where they failed. In the same way, offensive teams never discuss the 999 times they failed, only the final time when they succeed. **This leads to the feeling among DFIR folks that thinking they can stop APT:EquationShark (or even the local red team bros) is in vain — that they’re imposters. I would argue defense succeeds often; we just rarely acknowledge it.**

### The Jack of All Trades Inferiority

> _“I’m a worse RE than our RE and a worse 4n6 than our 4n6icator and a worse developer then our developer and a worse ops than our ops.”_

Shifting to an individual perspective, incident handlers are not [_T-Shaped People_](http://web.archive.org/web/20110329003842/http://www.chiefexecutive.net/ME2/dirmod.asp?sid=&nm=&type=Publishing&mod=Publications::Article&mid=8F3A7027421841978F18BE895F87F791&tier=4&id=F42A23CB49174C5E9426C43CB0A0BC46). While most people have one skill they’re a 8 of 10 on, and lots of skills they’re a 3 of 10 in, most DFIR types are a 5 out of 10 in four or five skills and 3s on the rest.

Because of this we [_Fake the Funk_](http://www.urbandictionary.com/define.php?term=fake+the+funk), assuming we should know more and trying to avoid admitting we don’t. This lack of self honesty to preserve face has caused me to wastes talented coworkers time & skill, wastes valuable learning experiences, and it has kept me from focusing on the tasks I do better than anyone.

**It’s easy to feel like an imposter when the rest of your team seems deeply skilled, even if it’s their area of expertise.** I’m not as good at working with malware as a RE, but I’m much better at reversing than most forensics engineers, and I know more about intelligence too. It’s a unique set of skills to see the big picture that has a unique and important place on a team.

### The “80/20” Inferiority

> _“About 80% of the time I just sit around being a mediocre software developer or systems engineer.”_

I structured this in the order of my imposter syndrome issues. I’m less concerned that RSA is going to release a _@SRoberts Replacement Box_ than the _Pentester Bros_ frustrate me by bragging about their conquests (and ignoring their defeats). The toughest? DFIR types live for emergencies in the way ER doctors live for injuries. What do you do when everything is healthy?

![80/20 Inferiority](https://miro.medium.com/max/700/0*5cVp702ESEIvKC1N.)

**No organization is without incidents, but the fact is that (even though there’s always something to do) there are also _non-emergency times_ where as an incident handler it’s easy to feel like a 3rd wheel, unnecessary, an _imposter_.** I spend a lot of that time building new systems, either as an ops engineer or a developer. This ties into the _Jack of All Trades_ issue, but I know I’m not nearly as good a developer as our real developers. Nor am I as good an ops engineer as our real ops engineers. It’s easy to feel somewhat ancillary until the next emergency.

### The “Human Being” Inferiority

Don’t think everyone feels like an imposter sometimes? I remember reading a note by a noteworthy colleague that no one would ever expect to feel like an imposter, writing a brutally honest account of feeling like others were going to find out she was a fraud. The text was a moment of pure humility on the author’s part. It didn’t say _woe is me_, but it was instead expressing a sense that she was handling this but wanted others to know it was normal and they could handle it too.

### So What’s the Solution?

- Acknowledge Imposter Syndrome is real. It’s not unique, you aren’t alone.
- Stop [_faking it until you make it_](http://www.entrepreneur.com/article/243629). Reach out to experts and either rely on them or learn from them.
- Use it as motivation. Feel like you’re weak in RE? Take some time to read [Practical Malware Analysis](http://www.nostarch.com/malware). Imposter Syndrome isn’t an excuse.
- Share your experience handling your own Imposter Syndrome with others.

### In The End

I often don’t feel like I’m prepared to be a part of this profession I’ve chosen. I feel like I should know more, read more, write more, and be a whole lot better at RE, forensics, coding, etc. I’m pretty sure all that is normal.

No one gets away from Imposter Syndrome entirely. It’s a human condition, but we can seek to understand it, to control it, and not let it control us. I think a willingness to confront this, with ourselves and our teams, can make everyone stronger.
