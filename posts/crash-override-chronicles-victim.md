---
title: "Crash Override Chronicles: Victim"
date: 2017-08-31T06:00:00.000Z
tags:
  - network-defense
  - ics
---

## Victim Sites & Technology

So all of those things were term or bits about generalized grid operations. What about the actual victim in this case. What was the equipment affected? Where was it?

### Ukrenergo

According to [Reuters](https://www.reuters.com/article/us-ukraine-crisis-cyber-attacks-idUSKBN1491ZF):

> Kovalchuk said the outage amounted to 200 megawatts of capacity, equivalent to about a fifth of the capital’s energy consumption at night.

There’s an interesting piece of data. 1/5 night capacity means one gigawatt (1000 megawatts) of total consumption at night. This got me wondering what the usual ratio of night vs day consumption is. A little Googling got me to [eia.gov’s article Demand for energy changes through the day](https://www.eia.gov/todayinenergy/detail.php?id=830). I’m doing some loose math but:

> 10.1 GW (🇺🇸 Lowest Night Demand) / 15.3 GW (🇺🇸 Peak Demand) \* 1 GW (🇺🇦 Low Demand) = 1.53 GW (🇺🇦 Peak Demand)

Is all that important? I don’t know, but I did the math and nothing wrong with demonstrating basic algebra skills. Mostly it’s useful for understanding scale.

## Notification

The folks from[Vsevolod Kovalchuk](https://www.facebook.com/permalink.php?story_fbid=1798082313797621&id=100007876094707):

> _This night at the substation “Severnaya” there was a malfunction in the control automatics.  
> As a result, at midnight there were disconnection of consumers from the northern part of the right bank of Kyiv and the surrounding districts of the Kyiv region. Our specialists quickly transferred the equipment to manual control mode and in 30 minutes they began to restore the power supply. Within an hour, the feed was fully restored to fifteen minutes.  
> We clarify the circumstances, the commission is already working. While the main version is external interference through data networks. Our cybersecurity experts promise to report in the near future.  
> We apologize to all those who stayed without electricity this night due to these events. Do not blame “Kyivenergo”, this time they are not guilty._

## Timeline

I tend to think about two different representations of an attack at the same time: The Graph & The Timeline. They serve two very different purposes as well as working together.

- [Electrum Timeline — Victim](https://docs.google.com/spreadsheets/d/1QFJ1mn8-Md9Vym9S_1SpU8i_jxZyLDA1qSr9mfqCuQs/edit#gid=0)
- [Threat Hunting Part 1: Improving Through Hunting](http://dragos.com/blog/20170831-ImproveThroughHunting.html)
- [Dragos Threat Hunting on ICS Networks - Part 2](http://dragos.com/blog/20170927-ThreatHuntingSeriesPart2.html)
