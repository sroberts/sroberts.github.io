---
title: Intelligence Concepts  -  The SANS Incident Response Process
date: 2015-05-18T05:00:00.000Z
tags:
  - network-defense
---

Getting away from the abstract to something a bit more distinctly DFIR we get to the (in)famous SANS Incident Response Process. The basis of [SANS 504: Incident Response & Hacker Techniques](http://www.sans.org/course/hacker-techniques-exploits-incident-handling) this process attempts to codify the typical incident process into key steps. **This is an essential process that helps form a cogent understanding of the incident process, but it’s limitations need to be just as well understood.**

## SANS Incident Response Process

![](https://cdn-images-1.medium.com/max/800/0*oT-5Rikrw1jK_EIg.)

- **Preparation:** Getting ready for incident response, creating documentation, building tools, etc.
- **Identification:** This is about the first moment where the victim becomes aware an attack has occurred, hopefully by an internal process or alert. Hopefully not thanks to [Brian Krebs](http://krebsonsecurity.com/) or the FBI.
- **Containment:** Containment is the processes of keeping further damage from occurring. This could involve deploying patches, blocking C2 access, or pulling a systems power cord out of the wall.
- **Eradication:** In a malware centric response this is about remediating compromised hosts, removing implants, etc.
- **Recovery:** Recovery is the process of restoring all business functions, such as bringing a compromised server back online.
- **Lessons Learned:** The most commonly forgotten aspect lessons learned is about asking the question “How can we do better next time?” and avoiding the same mistakes twice.

## A Walk Through the SANS Incident Response Process

The SANS IR Process focuses on a typical malware based event, focused on a single threaded incident and response. For this case we’ll walk through a typical remote access trojan based incident.

| Phase           | Description                                                                                                                                                                                                                                                                                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Preparation     | Strategic preparation includes deployment of sensors, development of processes, system & network hardening, etc. For a malware incident such as this tactical preparation includes deployment of signatures based on known indicators and heuristics.                                                                                                                                 |
| Identification  | Malware is most commonly identified in one of two ways. The ideal is before or right at the moment of deployment, generally speaking using a [wire-line product like FireEye](https://www.fireeye.com/products/nx-network-security-products.html) or an [intrusion detection system like Snort](https://www.snort.org/).                                                              |
| Containment     | In my experience this is the number one action that teams ignore. Teams often respond to malware incidents by jumping straight to eradication. In most cases that’s because containment requires manual intervention. The best teams are able to programmatically & remotely contain individual systems as well as entire subnets. This is a powerful capability and worth the effort. |
| Eradication     | This is the religious battle of the group. Some people trust AV to get rid of malware, but I come from the school of burn it down, wipe, and reload. Most malware is removable, but [take a look at Kaspersky’s Equation report](https://blog.kaspersky.com/equation-hdd-malware/7623/) and see how you feel.                                                                         |
| Recovery        | If you take the AV approach then once your antivirus runs and quarantines the malware I suppose you consider things recovered. If you choose to take my approach recovery tends to come from setting up a _new_ system and restoring from backups.\*                                                                                                                                  |
| Lessons Learned | After an incident the key is taking any and all information learned and putting it to further use (this is a nascent threat intelligence process). The importance can’t be over stated.                                                                                                                                                                                               |

> \* Aside: Make sure the backups themselves are clean as well. Nothing is worse than reintroducing an infection by restoring a malicious PDF or reinstalling a RAT.

## Rinse & Repeat

> _Fool me once, shame on you. Fool me twice, shame on me._

Malware analysis leads to new indicators and new detection. After action reports can show gaps in detection. Thus beginning a new preparation phase. This often happens in the form of an _[After-action Report](http://en.wikipedia.org/wiki/After-action_review)_.

## Takeaways from SANS Incident Response Process

**This process is a solid, basic understanding of the incident process that makes it easy to frame the common actions of an incident.** As responders get more advanced this process starts showing flaws since an incident response can’t be so rigid. Organizations never have a _preparation_ stage, always being under attack and never able to call a _time out_ to get their house in order. Stages like containment, eradication, and recovery often run concurrently. The process is malware centric, and becomes difficult to apply to other forms of incidents.

The other issue with the traditional SANS IR process was developed before the _beginning_ of intelligence driven incident response. It has no integration with external intelligence sources or dissemination. It’s useful in the short term, but we can do better.

## More IR Cycle Reading

- [SANS DFIR: The Big Picture of the Security Incident Cycle](http://digital-forensics.sans.org/blog/2010/09/27/digital-forensics-security-incident-cycle/)
- [SANS Reading Room: Incident Response Whitepapers](http://www.sans.org/reading-room/whitepapers/incident)
- [NIST: 800–61 Computer Security Incident Handling Guide](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf)
