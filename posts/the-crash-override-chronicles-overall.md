---
title: "The Crash Override Chronicles: Overall"
date: 2017-08-16T05:00:00.000Z
tags:
  - network-defense
  - ics
---

![](https://cdn-images-1.medium.com/max/2560/1*IQGo6uWopOatEUmWH0JA4g.png)

> Source: [Public Domain Pictures](http://www.publicdomainpictures.net/pictures/210000/velka/high-voltage-1485175963FQw.jpg)

In the first post of the [CRASH OVERRIDE Chronicles](https://medium.com/@sroberts/the-crash-override-chronicles-1c6191eb5330) I outlined my plan for reviewing Dragos' CRASHOVERRIDE report in order to build an understanding of the ICS threat landscape, key technologies, and ultimately one of the major actors involved. This second installment is a run through of the whole report calling out areas I need to focus on learning & investigating.

The first step was simple: _**[Read the report.](https://dragos.com/blog/crashoverride/CrashOverride-01.pdf)**_ The second step was also simple: _Read the report again; this time with a critical eye._ The first read through is for familiarity. The second read through is not simply to read but to pick out key phrases, items to focus on, and to look for bias and things I want to verify or follow up on. In addition, just for you dear reader, I took notes to call out positives and negatives I think make a difference in intelligence products.

![Crash Override login from Hackers](https://media.giphy.com/media/Q2W4hziDOyzu0/giphy.gif)

Because I had to use this at some point. Source: [Giphy](https://media.giphy.com/media/Q2W4hziDOyzu0/giphy.gif).

### Overall

Here are my generalized thoughts, as a CND focused analyst, looking at the Dragos report. They are in no particular order.

#### Things I Like

- **The Overall Aesthetic:** It’s easy to load reports down with meaningless graphics or extraneous pages which this report (mostly) avoided. It also has good use of color & graphics without looking like an art department had it as long as the research team did.
- **The Lack of Registration:** I have better things to do than invent stupid names to put in your registration page. Far easier for me, and far better analytics for them, to just link it directly.
- **Key Takeaways Up Front:** No, I don’t mean the _Executive Summary_. What I liked is the report’s one page _Key Takeaways_ section. It doesn’t just provide a [TL:DR](https://en.wikipedia.org/wiki/Wikipedia:Too_long;_didn%27t_read) but instead puts as much detail as possible on one page. If I ran a utility CND team I’d know most of what I’d need to know by the end of page two. I’m stealing this for my future products.
- **Introducing Unknown Concepts:** The section _Introduction to Electric Grid Operations_ is huge for folks like me. The ins-and-outs of industrial networks and their operations are largely unknown in the general security world (hence this blog series) so this context was enlightening. This was especially useful when reading the _Implications of capability_ section.
- **Historical Context:** Many incident responders have a general understanding of common malware attack patterns; mostly information stealing malware meant for intellectual property theft. ICS malware has a very different set of goals and thus different patterns. Calling out the few historic examples ([Stuxnet](https://www.wired.com/2014/11/countdown-to-zero-day-stuxnet/), [Havex](https://www.sans.org/reading-room/whitepapers/ICS/impact-dragonfly-malware-industrial-control-systems-36672), [Black Energy 2&3](https://www.kaspersky.com/resource-center/threats/blackenergy)) really helps contextualize CRASHOVERRIDE in an accessible way.
- **Calling out what was and wasn’t analyzed:** Very few incident response analyses are 100% comprehensive. There were multiple modules referenced in the CRASHOVERRIDE attacks that were missing. Mentioning those missing pieces is valuable for understanding analytical gaps and continued research opportunities.
- **Calling out other relevant research:** This was especially important given the concurrent release between Dragos and [ESET](https://www.eset.com/us/about/newsroom/press-releases/eset-discovers-dangerous-malware-designed-to-disrupt-industrial-control-systems/), but many companies write products acting like they were the sole team to ever analyze an attack or adversary. I liked the acknowledgment of other work being done on the same campaign.
- **Providing defensive actions that aren’t just a sales pitch:** The report provides seven recommendations for potential victims to protect themselves. None require proprietary systems, software, services, or for pay intelligence even if [all those are certainly available](https://dragos.com/product.html).

#### Things I Would Have Done Differently

- **Executive Summary:** The report didn’t really include a summary of the findings, just a summary of the report itself. I’d have included an extra sentence or two calling out key findings/actions that I could share with non-network defender stakeholders. Instead this was in the Key Takeaways section but both could be valuable to different audiences.
- **More Graphics:** Especially during the _Introduction to Electric Grid Operations_ section. This may have been hard in the quick turn around the Dragos team experienced but cliche as _a picture is worth a thousand words_ may be it’s also very true.
- **More Network IOCs:** Yara is great but depending on the organization Yara signatures may be difficult to widely deploy and detect on (unless Yara is way more prevalent in ICS environments than I would guess it is (which it could be)). Providing network signatures in a format like Snort could be more immediately effective to network defenders.
- **Aesthetic:** I don’t think the little graphy side bar did much. Small criticism, but I’d remove it given it didn’t serve much purpose for either content or branding.

Overall the pros far outweigh the cons and in general I think this is the kind of vendor report defenders need. Considerable technical detail, historical context, actionable recommendations, all with little to no marketing. This is a report aimed primarily at practitioners instead of purchasers.

### Learning

Based reading this report there are numerous areas I need to explore. These fall into context (learning about the environment where the attacks took place) and investigation (understanding the adversary and their actions). Here are my notes broken out using the [Diamond Model](http://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf) categories:

#### Victim (Environment)

Easily the portion I know the least about and thus will need the most research focus here are the key terms and concepts I’ll need to research:

- **Protocols:** DNP3 Protocol Stack, IEC 104, IEC101, & IEC 61850.
- **Terms:** RTUs, HMIs, OPC, OPC DA, PLCs, Intelligent Electronic Devices, ABB PCM600, & IOAs.
- **Technology Families:** Siemens SIMATIC, GE CIMPLICITY, & Advantech WebAccess.
- What is an electric grid feeder?
- What is the significance of voltage transforming?
- Dig into an introduction to SCADA & general architecture practices.

I don’t imagine this will be it. As I dig in I’m sure the current list will lead to more concepts & terms to learn about.

#### Capability (Investigation)

This report was largely about the malware used; CRASHOVERRIDE to Dragos and Industroyer to ESET. I’m not a reverser myself, but I can usually figure out most of what I need. There’s a lot to it:

- **Major Components:** Backdoor, 101 Payload, 104 Payload, 61850 Payload, OPC DA Payload, Wiper, Launcher. Their functions & uses (in SCADA environment manipulation).
- Malware Persistence Mechanisms
- Malware Actions & Attack Actions
- Command & Control Methods
- System & Network Detection & Discovery Course of Action Indicators
- Was there a corresponding espionage component that worked with CRASHOVERRIDE?

> The ultimate key of ICS attacks is not about the computer network operations understanding, but about the ICS operations & environment understanding.

#### Infrastructure (Investigation)

Honestly the Tor thing makes hunting for infrastructure… difficult. This might take a lot of work. I’m hoping context from digging into the Capability first will help.

- C2 IPv4 Addresses: `195.16.88.6, 93.115.27.57, 5.39.218.152`
- C2 Protocols? Encoding?

#### Adversary (Environment & Investigation)

My goal ultimately, and the general goal for most CND & CTI teams, is to understand the adversary aka ELECTRUM.

- Gather background on previous ICS tailored malware operations: Stuxtnet, BlackEnergy 2, BlackEnergy 3, & Havex/Dragonfly. Include geopolitics.
- Gather background on the Havex & Sandworm teams.
- Common Electrum TTPs.
- Whats the goal? What’s the impact? How disruptive is a few days of lost power vs a few weeks?

### Secondary Information Gathering

The original report is great but more the more data, especially primary source data, the better. The first step is ESETs concurrent release materials (ESET calls the CRASHOVERRIDE malware W32.Industroyer):

- ESET: [ESET discovers dangerous malware designed to disrupt industrial control systems](https://www.eset.com/us/about/newsroom/press-releases/eset-discovers-dangerous-malware-designed-to-disrupt-industrial-control-systems/)
- GitHub: [eset/malware-ioc](https://github.com/eset/malware-ioc/tree/master/industroyer) - Industroyer

The ESET analysis also provided a few secondary links that were intriguing:

- Reuters: [Ukraine’s power outage was a cyber attack: Ukrenergo](https://www.reuters.com/article/us-ukraine-cyber-attack-energy-idUSKBN1521BA)
- Vice: [The Ukrainian Power Grid Was Hacked Again](https://motherboard.vice.com/en_us/article/bmvkn4/ukrainian-power-station-hacking-december-2016-report)

#### Victim

The ESET articles provide a little bit of context for this, but no new concepts.

#### Capability

For analyzing the capability the best thing is the original malware. [ESET IOCs](https://github.com/eset/malware-ioc/tree/master/industroyer) and [Dragos IOCs](https://github.com/dragosinc/CRASHOVERRIDE/blob/master/CRASHOVERRIDE%20IOC%202016-06-12.csv) both provided hashes of the CRASHOVERRIDE malware. Dragos included two extra samples (which are indicated with `*`).

- F6C21F8189CED6AE150F9EF2E82A3A57843B587D
- CCCCE62996D578B984984426A024D9B250237533
- 8E39ECA1E48240C01EE570631AE8F0C9A9637187
- 2CB8230281B86FA944D3043AE906016C8B5984D9
- 79CA89711CDAEDB16B0CCCCFDCFBD6AA7E57120A
- 94488F214B165512D2FC0438A581F5C9E3BD4D4C
- 5A5FAFBC3FEC8D36FD57B075EBF34119BA3BFF04
- B92149F046F00BB69DE329B8457D32C24726EE00
- B335163E6EB854DF5E08E85026B2C3518891EDA8
- 7fAC2EDDF22FF692E1B4E7F99910E5DBB51295E6\*
- ECF6ADF20A7137A84A1B319CCAA97CB0809A8454\*

I was able to find & download nine of the eleven samples to analyze.

#### Infrastructure

ESET also had malware Command & Control IPv4 addresses. ESET had five, two more than Dragos. The ESET’s extras are indicated with \* this time:

- 5.39.218.152
- 46.28.200.132\*
- 93.115.27.5
- 188.42.253.43\*
- 195.16.88.6

#### Adversary

ESET focused heavily on the malware (hey they’re an AV vendor, can’t blame them) so there wasn’t a lot to add on the adversary front.

### The Industrial Control System Cyber Kill Chain

Love or hate the [original Lockheed Martin cyber kill chain](https://www.lockheedmartin.com/content/dam/lockheed/data/corporate/documents/LM-White-Paper-Intel-Driven-Defense.pdf) paper it’s a staple of the CTI and Incident Response world. In most cases the biggest criticism is it doesn’t fit every situation. It’s a valid criticism. Overall though frameworks are useful to contextualize complex events, so I also want to take the time and dig into the ICS Kill Chain paper. This paper contextualizes the traditional Kill Chain for ICS environments.

### A Final Thought

> “The CRASHOVERRIDE capability is purpose built to impact electric grid operations and has been created as a framework to facilitate the impact of electric grids in other countries in the future outside the attack that took place with it December 17th, 2016 in Ukraine. **However, as always, the defense is doable.**” ~ CRASH OVERRIDE Report

This post has broken down the core research for each upcoming post. Next week I’ll be sharing my research into the Victim aspects.
