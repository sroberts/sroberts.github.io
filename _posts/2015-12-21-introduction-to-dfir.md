---
layout: post
title: Introduction to DFIR
---

I talk a lot about Digital Forensics & Incident Response (DFIR) in terms of specific niches or esoteric issues, but what does someone who's brand new to the field needs to know to get started? DFIR, at least as I view it, is a broad field, so here are some of the basic of the things you should know as an introduction to DFIR and where to learn more. Each section will have:

- __A video:__ For an easy introduction.
- __A link:__ With more depth.
- __A tool:__ The _if you're going to know one tool this is the one_.
- __A book:__ To go deep into a subject you'll have a comprehensive resource.
- __A person:__ An expert in each subject who you'll want to keep an eye on.

## What is DFIR?

Digital Forensics & Incident Response is a multidiciplinary profession that focuses on identifying, investigating, and remediating computer network exploitation. This can take many forms and involves a wide variety of skills, kinds of attackers, an kinds of targets. We'll discuss those more below.

## Do you even want to be a DFIR?

First though lets start with a core question: Do you want to do DFIR? You'll need the following traits (not all, but at least a majority of them):

- __Curiosity:__ It's always about what you don't know.
- __Attention to Detail:__ You never know what bit of data makes the difference.
- __A Need for Variety:__ One day it's logs, the next it's packets, then memory.
- __Working with People:__ There's always an attacker and a victim.
- __The Taste for Blood:__ Great DFIR engineers want to win and hate to lose.

Want to know more about what DFIR takes? I recommend reading [The Cuckoo's Egg](http://www.amazon.com/The-Cuckoos-Egg-Tracking-Espionage/dp/1416507787/ref=pd_sim_14_17) by Clifford Stole.

## DFIR Skills

DFIR is a mix of hard (technical) and soft (people & process) skills. DFIR is a skill unto itself, so first I'll share some general overall resources, then get into specifics based on core DFIR skills.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link | Blog: [Journey into Incident Response](http://journeyintoir.blogspot.com/) |  http://detect-respond.blogspot.com/ |
| Tool | Redline & OSXCollector | Windows and OSX respectively. |
| Book | [Digital Forensics and Incident Response 3rd Edition](http://www.amazon.com/Incident-Response-Computer-Forensics-Edition/dp/0071798684) | The name is a give away, but it's a legitimately great book that covers the breath of IR. |
| Person | DFIR_Janitor | |

http://frodehommedal.no/presentations/first-tc-oslo-2015/#/slide-start
[Hunting](http://detect-respond.blogspot.com/2015/10/a-simple-hunting-maturity-model.html?view=sidebar)
[meirwah/awesome-incident-response](https://github.com/meirwah/awesome-incident-response)


## Hard Skills

Lets start with the core technical skills you'll need.

### Disk Forensics

When people think of the _DF_ in DFIR most think of dead disk forensics; ripping hard drives out of machines and analyzing them for compromise. This has evolved in the last 5 years to remote/enterprise forensics. Instead of removing hard drives analysts use software agents on every machine to analyze the file system.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [YouTube: Computer Forensics - File System Analysis using Autopsy](https://www.youtube.com/watch?v=6WKZAcRajbc) | |
| Link | http://www.hecfblog.com/ | | http://windowsir.blogspot.com/
| Tool | TSK/Autopsy | The default mature, open source solution.|
| Book | [Digital Forensics with Open Source Tools ](http://www.amazon.com/Digital-Forensics-Open-Source-Tools/dp/1597495867/ref=sr_1_9) by Cory Altheide & Harlan Carvey | |
| Person | | |

### Memory Forensics

Disk forensics is a mature capability and many organizations have gotten quite good at analyzing systems for compromise. As a result the attackers have moved, using techniques that emphasize usinge volitile storage, aka memory. Things like memory resident malware can't be detected on disk, so DFIRs had to move to analyzing memory itself.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | https://www.youtube.com/watch?v=3xAEsDT-4NA | |
| Link | http://memoryforensics.blogspot.com/ | |
| Tool | Volatility | The defacto standard. Also look at Rekall. |
| Book | The Art Of Memory Forensics |  |
| Person | @attrc | |

### Malware Triage

This is one where people will disagree with me. I don't think every DFIR needs to be a knee deep in assembly reverse engineer. Reverse Engineering is hard, one of the hardes skillsets out there, and isn't always 100% necessary (thogh often very useful). That said the ability to gather data from malware, at a high level, is incredibly essential and a set of skills every DFIR should have.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Lenny Zeltzer's Introduction to Malware Analysis](https://vimeo.com/9474345) | |
| Link |  | |
| Tool | [Yara]() | Also check out https://www.youtube.com/watch?v=TTLuy0gx5vE |
| Book | [Practical Malware Analysis](http://www.amazon.com/Practical-Malware-Analysis-Dissecting-Malicious/dp/1593272901/ref=pd_sim_14_21) | Easily the best book I've read for getting stronger in RE, this takes a very real world approach. |
| Person | @zeltzer | There are tons of amazing malware analysts. Lenny is the best _teacher_ of them all. |

### Network Forensics

Between malware analysis and , memory & disk forensics we've got analyzing hosts covered, but almost all incidents involve considerable network activity as well. Infections start as email or web browsing, malware beacons home, then exfiltratates data, all of which require understanding how to analyze network captures.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link |  | |
| Tool | Wireshark | |
| Book | [The Tao of Network Security Monitoring](http://www.amazon.com/Tao-Network-Security-Monitoring-Intrusion/dp/0321246772/ref=sr_1_3) | |
| Person | @Hectaman - Liam Randall | Doing some amazing stuff with the Bro network intrusion detection system. |

__Note:__ This is becoming increasingly difficult as encryption becomes more widely deployed. Finding ways to handle/work around data you can't always read is vital and one of the key reasons we also focus on the host.

### Attacker Methods

Blah blah blah Sun-Tzu is over quoted but the guy had a few good points. Knowing what your enemy does and how they do it, even in broad generalities, is incredibly useful. It's key to take the time to know what's easy, what's hard, and what's impossible.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Defcon 18: Kim Jong-il and Me How to Build a Cyber Army to Defeat the U.S. by Charlie Miller](https://www.youtube.com/watch?v=8AB3NcCkGNQ) | The best comprehensive introduction to what global exploitation looks like. |
| Link | [PassiveTotal Learn](https://www.passivetotal.org/learn) | Passive total is an amazing malicious infrastructure analysis tools. Their Learn site is all about understanding attacker infrastructure. |
| Tool | Metasploit Framework | |
| Book | [Hacking: The Art of Exploitation 2nd Edition](http://www.amazon.com/Hacking-Art-Exploitation-Jon-Erickson/dp/1593271441/ref=sr_1_2) | |
| Person | @egypt | |

### Intelligence Analysis

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link | [Christian: A Quick Look at A Likely NewPOSThings Sample](http://www.cyintanalysis.com/a-quick-look-at-a-likely-newposthings-sample/) | Starting with a simple hash this intel analysis goes deep into the infrastructure of a POS malware tool. |
| Tool | Maltego | |
| Book | | |
| Person | @n300trg - Tom Creedon | |

### OSINT

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | https://www.youtube.com/watch?v=JxJaCIzzFzg | |
| Link |  | |
| Tool | Shodan | |
| Book | | |
| Person | @roeloftemmingh | One of the Maltego developers. Good mix of things. |

### Development

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link |  | |
| Tool | Python | People will argue, but it's my go to. Also look at Go. |
| Book | | |
| Person | @pidydx | |

## Soft Skills

### Operational Security

Security as a DFIR is an important thing. In many cases
http://motherboard.vice.com/read/cybersecurity-researchers-are-hunted-from-all-sides

@jessysaurusrex

### Investigation Process & Analysis

## T Shaped People
![T-Shaped People](https://docs.google.com/drawings/d/1c6xxt6JktO08HT6fIxEaCW50fVjHRvGnzbpECPMUmqk/pub?w=960&h=720)
