---
title: The Crash Override Chronicles
date: 2017-08-08T05:00:00.000Z
tags:
  - network-defense
  - ics
---

I’ve been lucky and had a really wide variety of experiences in information security throughout my career. Government & non-government. Vendor & practitioner. Finance & dotcom. I’ve seen a lot of stuff. It’s to the point that I get even more excited about the stuff I’ve never done. One of those moments happened a few weeks ago when the [Dragos](https://dragos.com) team released their [Crash Override](https://dragos.com/blog/crashoverride/CrashOverride-01.pdf) report.

> **Full Disclosure:** I know a few of the folks over at Dragos and consider them friends but friends that value good, even critical, analysis.

![](https://cdn-images-1.medium.com/max/800/1*UbFDIcy1RzIJJrr2aQXOMQ.png)

Source: [Crash Override Report by Dragos](https://dragos.com/blog/crashoverride/CrashOverride-01.pdf)

The Crash Override report is an investigation into a campaign against an electric utility infrastructure in Ukraine. Now I don’t know a lot about Industrial Control System (ICS) security, so a report like this is fascinating to me. It’s a view into a whole different world, a different type of network & system infrastructure, a different set of response actions, new stakeholder needs, and an adversary with TTPs I don’t even know. While moving from finance network defense to dotcom network defense had a lot of overlap (both largely privacy focus) ICS networks are totally different (such as a bigger focus on availability).

Between self driving cars, the connected grid, IOT, robotics, etc I think industrial networks and attacks are a growing area of risk and I’m not alone ([Kaspersky](https://ics-cert.kaspersky.com/reports/2017/03/28/threat-landscape-for-industrial-automation-systems-in-the-second-half-of-2016/) & [HuffPo](http://www.huffingtonpost.com/daniel-wagner/the-growing-threat-of-cyb_b_10114374.html) to start). Enough so that I feel like I need to know more. Thus the Crash Override Chronicles, my series digging into this report and likely a lot of secondary things that come out of it. I’m planning a structured approach digging into a few different aspects of Crash Override.

### The Plan

I’m planning to break down my understanding based on the following five posts which I’m calling the Crash Override Chronicles:

- **[Overall Report:](https://medium.com/@sroberts/the-crash-override-chronicles-overall-8389ef178fdf)** A run through of the whole report calling out areas I need to focus on learning or investigating.
- **Victim — Domain Understanding:** I know I don’t know much about the ICS domain and the power generation/transport world. I’m going to focus on gaining context.
- **Capability — Crash Override Malware:** The report focused on the specific piece of malware the adversary used called Crash Override. Time for some malware analysis.
- **Infrastructure — Crash Override Infrastructure:** Malware does not operate alone, even in the ICS world ([nope, even the one you think worked by itself](https://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/w32_stuxnet_dossier.pdf)). There’s always infrastructure for delivery, command & control, and often actions over target.
- **Adversary — Electrum:** Lastly I’d like to take all this and dig into the adversary behind the Crash Override campaign. There’s been a lot of speculation, and I don’t make any promises, but it makes a good conclusion.

For those of you playing at home you’ll notice that these four characteristics (Victim, Capability, Infrastructure, and Adversary) make up the 4 points of the [Diamond Model](http://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf). This was totally accidental as I laid this project out, but the model emerged, and so I’m making that a part of the plan.

![Woot](https://media.giphy.com/media/xTiTnLtsaXt2sALsyc/giphy.gif)

Source: [Giphy](https://media.giphy.com/media/xTiTnLtsaXt2sALsyc/giphy.gif)

I’ll be posting once a week on Tuesdays. See you on August 15th. 👋
