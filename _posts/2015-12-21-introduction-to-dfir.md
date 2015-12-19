---
layout: post
title: Introduction to DFIR
---

I talk a lot about Digital Forensics & Incident Response (DFIR) in terms of specific niches or esoteric issues, but what does someone who's brand new to the field needs to know to get started? DFIR, at least as I view it, is a broad field, so here are some of the basic of the things you should know as an introduction to DFIR and where to learn more.

Each section will have:

- A video: For an easy introduction.
- A link: With more depth.
- A tool: Hopefully the _if you're going to know one tool this is the one_, though I'll cheat and do two a few times.
 - A book: So if you want to go deep into a subject you'll have a comprehensive resource.
 - A person: An expert in each subject who you'll want to keep an eye on.

## What is DFIR?

Digital Forensics & Incident Response is a multidiciplinary profession that focuses on identifying, investigating, and remediating computer network exploitation. This can take many forms and involves a wide variety of skills, kinds of attackers, an kinds of targets. We'll discuss those more below.

## Do you even want to be a DFIR?

First though lets start with a core question: Do you want to do DFIR? You'll need the following traits (not all, but at least a majority of them):

- Curiosity
- Attention to Detail
- A Need for Variety
- Working with People and Computers
- The "Taste of Blood"

## DFIR Skills

DFIR is a mix of hard (technical) and soft (people & process) skills. DFIR is a skill unto itself, so first I'll share some general overall resources, then get into specifics based on core DFIR skills.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link | Blog: [Journey into Incident Response](http://journeyintoir.blogspot.com/) | |
| Tool | Redline & OSXCollector | Windows and OSX respectively. |
| Book | [Digital Forensics and Incident Response 3rd Edition](http://www.amazon.com/Incident-Response-Computer-Forensics-Edition/dp/0071798684) | The name is a give away, but it's a legitimately great book that covers the breath of IR. |
| Person | DFIR_Janitor | |

## Hard Skills

Lets start with the core technical skills you'll need.

### Disk Forensics

When people think of the DF in DFIR most think of dead disk forensics, IE ripping hard drives out of machines and analyzing them for compromise. This has evolved of late to remote/enterprise forensics. Instead of removing hard drives analysts use software agents on every machine to analyze the file system.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link |  | |
| Tool | TSK/Autopsy | The default mature, open source solution.|
| Book | | |
| Person | | |

- Encase ($) & FTK ($) - The two defacto paid packages. Both run standalone or Enterprise.
- TSK/Autopsy - The biggest open source toolkit and the best place to get started.

### Memory Forensics

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link |  | |
| Tool | Volatility | The defacto standard. Also look at Rekall. |
| Book | The Art Of Memory Forensics |  |
| Person | @attrc | |

### Malware Triage

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Lenny Zeltzer's Introduction to Malware Analysis](https://vimeo.com/9474345) | |
| Link |  | |
| Tool | Yara | |
| Book | | |
| Person | | |

https://zeltser.com/malware-analysis-webcast/

### Network Forensics

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link |  | |
| Tool | Wireshark | |
| Book | | |
| Person | @Hectaman - Liam Randall | Doing some amazing stuff with the Bro network intrusion detection system. |

### Attacker Methods

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Defcon 18: Kim Jong-il and Me How to Build a Cyber Army to Defeat the U.S. by Charlie Miller](https://www.youtube.com/watch?v=8AB3NcCkGNQ) | The best comprehensive introduction to what global exploitation looks like. |
| Link | | |
| Tool | Metasploit Framework | |
| Book | | |
| Person | @egypt | |

### Intelligence Analysis

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link | | |
| Tool | Maltego | |
| Book | | |
| Person | @n300trg - Tom Creedon | |

### OSINT

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link | | |
| Tool | Maltego | |
| Book | | |
| Person | @roeloftemmingh | One of the Maltego developers. Good mix of things. |

### Development

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | | |
| Link |  | |
| Tool | Python | People will argue, but it's my go to. Also look at Go. |
| Book | | |
| Person | | |

## Soft Skills

### Operational Security

Security as a DFIR is an important thing. In many cases
http://motherboard.vice.com/read/cybersecurity-researchers-are-hunted-from-all-sides

@jessysaurusrex

### Investigation Process & Analysis

## T Shaped People
![T-Shaped People](https://docs.google.com/drawings/d/1c6xxt6JktO08HT6fIxEaCW50fVjHRvGnzbpECPMUmqk/pub?w=960&h=720)
[meirwah/awesome-incident-response](https://github.com/meirwah/awesome-incident-response)
[PassiveTotal Learn](https://www.passivetotal.org/learn)
