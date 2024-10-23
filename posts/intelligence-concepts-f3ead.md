---
title: Intelligence Concepts — F3EAD
date: 2015-03-24T05:00:00.000Z
tags:
  - intelligence
---

One of the most talked-about intelligence concepts in information security today is [F3EAD](https://smallwarsjournal.com/jrnl/art/f3ead-opsintel-fusion-“feeds”-the-sof-targeting-process). Standing for Find, Fix, Finish, Exploit, Analyze, and Disseminate, this is a methodology for combining operations (in this case we’re talking about _kinetic ops_) and the intelligence process. While the [Intelligence Cycle](http://sroberts.github.io/2015/02/16/cycles-intelligence/) & [SANS IR cycle](http://sroberts.github.io/2015/03/18/sans-ir/) are both useful, they are ultimately academic. If the goal is Intelligence-Driven Incident Response, we need to combine intelligence with ops, and that’s where F3EAD shines.

> **_An Aside: Military Terminology in Security_**  
> A fundamental discussion that often comes up when you discuss intelligence (and a lot of other parts of information security) is the use of military terminology. This is a divided issue. The fact is that war is the single oldest and most studied adversarial conflict, and while security doesn’t have the gravity of a military conflict, I do find that the military has much to teach us.

### F3EAD

![](https://cdn-images-1.medium.com/max/800/0*ajB31jTnMsyfCtVC.jpg)

_**Source:** [Small Wars Journal - F3EAD: OPS/INTEL FUSION “FEEDS” THE SOF TARGETING PROCESS](https://smallwarsjournal.com/sites/default/files/F3.jpg)_

F3EAD is about combining the operations cycle with the intelligence cycle so that they both feed each other. This process rose during the wars Afghanistan & Iraq (the second time) the teams involved were special forces (operations) and traditional all source intelligence teams (intelligence). We’ll break this into two major sections:

### Operations:

- **Find:** The F3EAD process starts with targeting, deciding who the focus of the operation is.
- **Fix:** Identify where the adversary is.
- **Finish:** Use the processed information to complete a predetermined operational objective.

In a _[kinetic scenario](http://en.wikipedia.org/wiki/Kinetic_military_action)_, this process could start with a special operations team deciding to target a high ranking former regime member. Using available intelligence and telemetry, the team locates that target and initiates the operation to capture the target. After the capture the team may take material related to the capture, including files, computers, and information from interrogations, and pass that to the intelligence team.

### Intelligence:

- **Exploit:** At this point all information developed during the operations section is collected and enhanced. This can be correlated to the collection and processing steps in the intelligence process.
- **Analyze:** The analyze process is the same as in the intelligence process: taking the collected information, developing it further, in this case to support the next find, fix, finish cycle.
- **Disseminate:** Share the developed intelligence with relevant stakeholders including operations and other intelligence teams.

Following the operation, the intelligence team then begins their cycle based on the outputs from the operations team. This follows the traditional intelligence cycle process, but the key is the expected input and outputs are meant to enable operations. **Thus operations enables the intelligence gathering while the intelligence enables further operations.** In most cases, this tight coupling isn’t just based on products, but even putting the teams physically in close proximity to enable this [synergy](http://cdn.meme.am/instances/58776835.jpg).

### A Walk Through the F3EAD Cycle

![](https://cdn-images-1.medium.com/max/800/0*K5Gbn5u1Adc9LoU-.jpg)

_**Source:** [IMDB - Zero Dark Thirty (2012)](https://www.imdb.com/title/tt1790885/mediaviewer/rm678930432/)_

Even if you don’t have a team of M-4 wielding SEALs (I know, seems like an oversight), the idea of combining operations with intelligence is the exact goal of that favorite buzz phrase: **intelligence driven incident response.**

|                 |                                                                                                                                                                                                                                                                                                                                                                                                           |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Find**        | _Vendor X_ releases a new report about a new threat group operating in your vertical. You use this report as the beginning of your targeting.                                                                                                                                                                                                                                                             |
| **Fix**         | The vendor report include indicators, which the incident response team uses to identify a group of compromised hosts. In some cases, depending on resources, an incident response team may enhance these.                                                                                                                                                                                                 |
| **Finish**      | The incident response team remediates the compromised hosts.                                                                                                                                                                                                                                                                                                                                              |
| **Exploit**     | Here’s the key: after the _finish/remediation_ the information collected during the incident response is gathered. This includes the information that started the F3 cycle (in this case the vendor report) but should also include the malware identified during the incident, network captures, information about the infrastructure, & anything and everything identified during the operations piece. |
| **Analyze**     | The intelligence team analyzes all the collected information. Their goal is to develop further targeting. A good example would be identifying other IP addresses associated with C2 domains using a tool like [PassiveTotal](https://www.passivetotal.org/).                                                                                                                                              |
| **Disseminate** | The intelligence developed during the _Analyze_ step is disseminated to other stakeholders. This includes the original operations team.                                                                                                                                                                                                                                                                   |

### Takeaways from F3EAD

At its core, F3EAD speaks directly to two of the biggest challenges with the rise of the _Threat Intelligence_ concept:

- How is intelligence converted from data into action?
- How are the results of security team actions converted into ongoing intelligence?

The first question gets nearly all the attention, and is certainly an interesting concept, but the second one is often the most applicable. Incident Response teams looking to improve often ask where to start with threat intelligence, a feed, a product, etc. In my mind the best answer, addressed by F3EAD, is to start with your own incidents. Teams can find amazing value in mining their past incidents, and at a price that beats any threat intelligence product.

### More Resources

- [Fishnet Security 6Labs Blog: Applying the Military’s F3EAD Framework to Cyber Threat Intelligence](https://www.fishnetsecurity.com/6labs/blog/applying-militarys-f3ead-framework-cyber-threat-intelligence)
- [Small Wars Journal: F3EAD: Ops/Intel Fusion “Feeds” The SOF Targeting Process](http://smallwarsjournal.com/jrnl/art/f3ead-opsintel-fusion-%E2%80%9Cfeeds%E2%80%9D-the-sof-targeting-process)
