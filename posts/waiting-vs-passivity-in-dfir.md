---
title: Waiting vs Passivity in DFIR
date: 2016-12-10T00:00:00.000Z
tags:
  - network-defense
---

![](https://cdn-images-1.medium.com/max/800/1*C0Ox9jAP5sINIZlxyM1ZUg.png)

> From the New York Times: [“Review: ‘Hamilton,’ Young Rebels Changing History and Theater”](http://www.nytimes.com/2015/08/07/theater/review-hamilton-young-rebels-changing-history-and-theater.html)

Give it a second, I’ll explain the Hamilton reference to DFIR, but for now let me share one of my favorite songs. [Aaron Burr](https://en.m.wikipedia.org/wiki/Aaron_Burr) thinks [Alexander Hamilton](https://en.m.wikipedia.org/wiki/Alexander_Hamilton) is a brash aggressive brute and believes Hamilton thinks him slow and unwilling to make a decision. Burr then sings this song to explain his true goals: [Wait for It by the cast of Hamilton](https://www.youtube.com/watch?v=k9AyO8h2I0k).

Burr ends up having an iconic line about 3/4 of the way through the song:

- **BURR:** I’m not falling behind or running late
- _ENSEMBLE:_ Wait for it, Wait for it, Wait for it, Wait for it
- **BURR:** I’m not standing still, I am lying in wait`

I’d heard this line dozens of times (yeah I admit, I’m a bit obsessed) but it struck me a bit differently recently. In this case I was monitoring a resource being used by an espionage group in carrying out their attacks. The question came up: Do we notify the owner and effectively _burn_ the resource making it unusable by the attacker while losing telemetry or continue to monitor it and gain intelligence but risk it still being used against victims.

It was a tough choice that ended with us setting a series of conditions for determining if it was still gaining intelligence. I ended up framing this cost vs benefit analysis in the terms Aaron Burr uses in Hamilton: In our investigation what was happening? Were we simply standing still (being passive) or lying in wait (actively avoiding action in furtherance of a more decisive action later).

Sometimes people claim investigations need to always fix things and move, but sometimes the best thing for an investigation is to take the time to see what's happening and plan the next steps. That shouldn't be mistaken for passivity. But when do you hold and when do you move forward?

Unfortunately I can’t really help you with this one. This takes a combination of experience and intuition. While I can’t give you a solid answer here are some key questions to ask yourself:

- Are you gaining meaningful intelligence?
- Is gaining more information in the best interest of victims as well as the team collecting?
- Are you able to exploit the information you’re gathering in order to act on it in an effective and timely manner?

If you answer yes to those then the best course of action is continuing collection until you’ve gained as much value as possible. The key is to keep revisiting these questions on a regular basis until there is a change. At that point you must be prepared to act, whether that’s remediating your network, notifying a victim, or sharing the intelligence you’ve gathered with others.

The last thing to consider about balancing the collection vs. action question is the pressure that can come with it. This can come from many directions, inside your team, your boss, impacted users, law enforcement, etc. The argument is straightforward and compelling: fix the problem and move on to other things.

In the end you not only have to decide for yourself but make your case to stakeholders, especially superiors. You have to be prepared to push back against others as long as you’re getting meaningful collection and developing intelligence. If you can’t get buy in then the best choice is to hand off information as soon as possible.

Hamilton himself probably said the best thing about the need to remain strong in situations like this…

![](https://cdn-images-1.medium.com/max/600/1*s8TOY6IHjavXR0m1W830KQ.png)

> Those who stand for nothing fall for anything. _~ Alexander Hamilton_
