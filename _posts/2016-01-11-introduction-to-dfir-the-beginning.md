---
layout: post
title: Introduction to DFIR
---

One of my favorite things is talking to students and people new to the security field. It feels like yesterday I was wandering around the first [Shmoocon](http://shmoocon.org/) as a student in awe of the people I met and the work they were doing. Now I'm 10 years into my career and have a whole different perspective (though still in awe with those folks). Starting a career in infosec isn't easy and while [there are better general introductions](http://tisiphone.net/2015/10/12/starting-an-infosec-career-the-megamix-chapters-1-3/) I wanted to add my perspective on getting started in Digital Forensics and Incident Response (DFIR).

## What is DFIR anyway?

Digital Forensics & Incident Response is a multidisciplinary profession that focuses on identifying, investigating, and remeidating computer network exploitation. This can take varied forms and involves a wide variety of skills, kinds of attackers, an kinds of targets. We'll discuss those more below.

First though lets start with a core question: Do you want to do DFIR? You'll need the following traits (not all, but at least a majority of them):

- __Curiosity:__ It's always about what you don't know.
- __Attention to Detail:__ You never know what bit of data makes the difference.
- __A Need for Variety:__ One day it's logs, the next it's packets, then memory.
- __Working with People:__ There's always an attacker and a victim.
- __An Affinity for Stress:__ You don't have to like it, but you must handle it.
- __The Taste for Blood:__ Great DFIR engineers want to win and hate to lose.

Want to know more about what DFIR looks like? I recommend reading [The Cuckoo's Egg](http://www.amazon.com/The-Cuckoos-Egg-Tracking-Espionage/dp/1416507787/ref=pd_sim_14_17) by Clifford Stoll. If that gets you excited journey on!

DFIR is a broad field so here are some of the basic of the things you should know as an introduction to DFIR and where to learn more. Over the coming days I'm going to post about various topics in DFIR (more below) and people learn differently I will provide different types of resources. Each topic will have:

- __A video:__ For an easy broad introduction.
- __A link:__ To a site focused on that topic.
- __A tool:__ The _if you're going to know one tool this is the one_.
- __A book:__ To go deep into a subject you'll have a comprehensive resource.
- __A person:__ An expert in each subject who you'll want to learn from.

Lets get started.

## DFIR Skills

DFIR is a mix technical and soft (people & process) skills. DFIR is a skill unto itself we'll start with some general resources then get into specifics.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Threat Analysis of Complex Attacks](https://www.youtube.com/watch?v=Yh1XZf0hLS4) | From SANS DFIR Summit in 2015. Shows the variety of skills across IR analyzing an interesting attack. |
| Link | [Journey into Incident Response](http://journeyintoir.blogspot.com/) | Corey is a veteran incident responder who shares tons of resources big and small on his blog. |
| Tool | [Redline](https://www.fireeye.com/services/freeware/redline.html) & [OSXCollector](http://yelp.github.io/osxcollector/) | Live response tools. Windows and OSX respectively. Try them out on your own systems. |
| Book | [Digital Forensics and Incident Response 3rd Edition](http://www.amazon.com/Incident-Response-Computer-Forensics-Edition/dp/0071798684) | The name is a give away, but it's a legitimately great book that covers the breath of IR. |
| Person | [@jackcr](https://www.twitter.com/jackcr) - Jack Crook | Jack's Twitter feed is a letter to new analysts. Easy things to learn and hard truths in the same breath. Every DIFR should read it. Honorable Mention to [@hacks4pancakes](https://twitter.com/hacks4pancakes). |

## Technical Skills

The first category of skills that I split DFIR into is technical skills. These are hands on keyboard skills focused on levels of an investigation.

### File System Forensics

When people think of the _DF_ in _DFIR_ most think of filesystem forensics; ripping hard drives out of machines and analyzing them for compromise. This has evolved in the last 5 years to remote/enterprise forensics. Instead of removing hard drives analysts use software agents on every machine to analyze the file system.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [DFIR using SIFT Workstation](https://www.youtube.com/watch?v=w1ygCP2TeCY) | [SIFT Workstation](http://digital-forensics.sans.org/community/downloads) is a forensics environment created by SANS is is a great place for both new and experienced analysts. The speaker is Rob Lee. Nuff said. |
| Link | [Hacking Exposed: Computer Forensics](http://www.hecfblog.com/) | To call David Cowen prolific is an undersell. His [blog](http://www.hecfblog.com/), [book](https://www.goodreads.com/book/show/18769673-hacking-exposed-computer-forensics), [Twitter](https://twitter.com/HECFBlog), & [podcast](https://www.youtube.com/user/LearnForensics) are all can't miss. Not to mention a darn nice guy. |
| Tool | [TSK/Autopsy](http://www.sleuthkit.org/) | The default mature, open source solution.|
| Book | [Digital Forensics with Open Source Tools ](http://www.amazon.com/Digital-Forensics-Open-Source-Tools/dp/1597495867/ref=sr_1_9) | I'm always partial to open source and this shows how much you can do without spending a dime on Encase. |
| Person | [@iamevltwin](https://www.twitter.com/iamevltwin) - Sarah Edwards | If you're looking for Mac forensics you want Sarah. Her [Mac4n6](http://www.mac4n6.com/) site is the go to source for Mac and her Twitter is full of great info. |

### Memory Forensics

Disk forensics is a mature capability and many organizations have gotten quite good at analyzing systems for compromise. As a result the attackers have moved, using techniques that emphasize using volatile storage, aka memory. Things like memory resident malware can't be detected on disk, so DFIRs had to move to analyzing memory itself.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Memory Forensics for Incident Response](https://www.youtube.com/watch?v=3xAEsDT-4NA) | I'm not big into memory forensics, so I learned a lot from this SANS DFIR Webcast. I think it's a solid starting resource. |
| Link | [Volatility Labs](http://volatility-labs.blogspot.com/) | If you're doing memory analysis with Volatility (and it's where I'd start) you want the Volatility blog. |
| Tool | [Volatility](http://www.volatilityfoundation.org/) | The defacto standard. Also look at [Google's Rekall](http://www.rekall-forensic.com/). |
| Book | [The Art Of Memory Forensics](https://www.goodreads.com/book/show/19525138-the-art-of-memory-forensics) | A 4.6 rating on GoodReads and the recommendation of all the memory analysis folks I know is enough for me. |
| Person | [@attrc](https://www.twitter.com/attrc) - Andrew Case | I hear he's taken a course on Memory Forensics. And was a core Volatility dev. And wrote the Art of Memory Forensics. |

### Network Forensics
Between malware analysis and , memory & disk forensics we've got analyzing hosts covered, but almost all incidents involve considerable network activity as well. Infections start as email or web browsing, malware beacons home, then exfiltratates data, all of which require understanding how to analyze network captures.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Network Forensics What Are Your Investigations Missing](https://www.youtube.com/watch?v=cVbil4y702o) | Phil Hagan wrote the book... er... course on advanced Network Forensics, but this introduction is pretty awesome. This is a great overview of what you can do with Network Forensics. |
| Link | [Pcapr](http://www.pcapr.net/home) | The toughest thing with learning network forensics is having interesting pcaps to look at. This collection has some of everything, from DDoS to Malware. Just what the doctor ordered. |
| Tool | Wireshark | The defacto tool for ripping apart packets is Wireshark. Learn more about it [here](https://www.youtube.com/watch?v=UXAHvwouk6Q). |
| Book | [The Tao of Network Security Monitoring](http://www.amazon.com/Tao-Network-Security-Monitoring-Intrusion/dp/0321246772/ref=sr_1_3) | I think every Network Analysis type I know cut their teeth with Tao. Somewhat dated now, but the seminal work on the topic. |
| Person | [@Hectaman](https://www.twitter.com/Hectaman) - Liam Randall | Doing some amazing stuff with the Bro network intrusion detection system. |

> __Addition:__ @[Richard Bejtlich](https://twitter.com/taosecurity) & @[Chris Sanders](https://twitter.com/chrissanders88) both reached out to me suggesting I look at Richard's newer book: [The Practice of Network Security Monitoring: Understanding Incident Detection and Response](https://www.goodreads.com/book/show/17346927-the-practice-of-network-security-monitoring). Chris also mentioned his book: [Practical Packet Analysis: Using Wireshark to Solve Real-World Network Problems](https://www.goodreads.com/book/show/845795.Practical_Packet_Analysis). I mentioned Tao since it was the book I cut my teeth on, but these gentlemen are correct; these are better modern options. Both are on my reading list now.

__Note:__ This is becoming increasingly difficult as encryption becomes more widely deployed. Finding ways to handle/work around data you can't always read is vital and one of the key reasons we also focus on the host.

### Malware Triage

This is one where people will disagree with me. I don't think every DFIR needs to be a knee deep in assembly reverse engineer. Reverse Engineering is hard, one of the hardest skillsets out there, and isn't always 100% necessary (though often very useful). That said the ability to gather data from malware, at a high level, is incredibly essential and a set of skills every DFIR should have.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Lenny Zeltzer's Introduction to Malware Analysis](https://vimeo.com/9474345) | There are only a handful speakers I will always take the chance to hear. Lenny is one of them. I learn something every single time. |
| Link | [Malwr](https://malwr.com/) | So this is actually a tool which analyzes malware by running it but it's also a great place to experiment and learn. |
| Tool | [Yara](https://plusvic.github.io/yara/) | It's basically AV you control. Also check out [this intro video](https://www.youtube.com/watch?v=TTLuy0gx5vE). |
| Book | [Practical Malware Analysis](http://www.amazon.com/Practical-Malware-Analysis-Dissecting-Malicious/dp/1593272901/ref=pd_sim_14_21) | Easily the best book I've read for getting stronger in RE, this takes a very real world approach. |
| Person | [@zeltzer](https://www.twitter.com/zeltzer) - Lenny Zeltzer | There are tons of amazing malware analysts. Lenny is the best _teacher_ of them all. |

### Log Analysis

Log analysis is actually the technical skill we talk about the least, but end up doing the most. [SIEM](https://en.wikipedia.org/wiki/Security_information_and_event_management)s were supposed to keep us from needing to do this, but most of the better DFIRs I know still spend a considerable amount of their time dug into a logging console. Logs can be analyzed system by system, but the real power shows up when you search logs at enterprise scale. It's tool driven, but the skills are the same for most of them.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Incident Response Event Log Analysis](https://www.youtube.com/watch?v=Xw536W7kbDQ) | There aren't a lot of great log centric resources out there. This was the best video I could find. Someone should fix this.  |
| Link | [Enterprise Detection & Response](http://detect-respond.blogspot.com/) | David's blog is log centric, but focused on all of IR. It's been the source of some of the bigger ideas in IR. A must read. |
| Tool | [ElasticSearch + Logstash + Kibana](https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elk-stack-on-ubuntu-14-04) | You could pay for [Splunk](http://www.splunk.com/), but how would you save for that mega yacht you've always wanted? [ELK](https://www.elastic.co/products) gives you most of the log hunting goodness with none of the price. |
| Book | [Logging and Log Management: The Authoritative Guide to Understanding the Concepts Surrounding Logging and Log Management](https://www.goodreads.com/book/show/14501544-logging-and-log-management) | I'll be honest, I haven't read this book, but it's the first one I would read. In fact it's on my list. |
| Person | [@DavidJBianco](https://twitter.com/DavidJBianco) - David J. Bianco | He coined the idea of [Hunting](http://detect-respond.blogspot.com/2015/10/a-simple-hunting-maturity-model.html). The [Pyramid of Pain](http://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html). And he's a really nice guy. |

### Intelligence Analysis

I already talk a lot about Threat Intelligence ([1](http://sroberts.github.io/2015/03/24/f3ead/), [2](http://sroberts.github.io/2015/03/18/sans-ir/), [3](http://sroberts.github.io/2015/02/16/cycles-intelligence/), [4](http://sroberts.github.io/2015/01/27/cycles-ooda/)). It's a complicated and nuanced subject but it's impact is undeniable. Being able effectively use these structured approaches to enhancing data (no, that CSV file you downloaded isn't intelligence) can make teams faster and more precise.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Cyber Intelligence Concrete Analysis in a Fluid World ](https://www.youtube.com/watch?v=YS9f1a6T_b4) | I found this while researching this post. Good overview by [Coleman Kane](https://twitter.com/colemankane). |
| Link | [Christian: A Quick Look at A Likely NewPOSThings Sample](http://www.cyintanalysis.com/a-quick-look-at-a-likely-newposthings-sample/) | Starting with a simple hash this intel analysis goes deep into the infrastructure of a POS malware tool. |
| Tool | [Maltego](https://www.paterva.com/web6/products/maltego.php) | Intelligence isn't about tools, but tools are really helpful. Having a graphing tool makes bringing multiple datasets really powerful. Given Palantir is $$$ my go to is Maltego. |
| Book | [Structured Analytic Techniques For Intelligence Analysis](https://www.goodreads.com/book/show/7818985-structured-analytic-techniques-for-intelligence-analysis) | This is one of the heaviest books I recommend, and I'm only part way through, but it's changed my approach. |
| Person | [@CYINT_dude](https://twitter.com/CYINT_dude) - CYINT_dude | I don't honestly know who this is, but I love basically all their tweets. Does a really great job tying cyber actions to real life impacts. |

> __Addition:__ @[y0m](https://twitter.com/y0m) reached out to recommend adding the [Psychology of Intelligence](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis/PsychofIntelNew.pdf) by Richard J Heuer Jr. I couldn't agree more. Actually the [CIA Center for Intelligence Studies](https://www.cia.gov/library/center-for-the-study-of-intelligence/) is full of great resources.

### Attacker Methodology

Blah blah blah Sun-Tzu is over quoted but the guy had a few good points. Knowing what your enemy does and how they do it, even in broad generalities, is incredibly useful. It's key to take the time to know what's easy, what's hard, and what's impossible.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Defcon 18: Kim Jong-il and Me How to Build a Cyber Army to Defeat the U.S. by Charlie Miller](https://www.youtube.com/watch?v=8AB3NcCkGNQ) | The best comprehensive introduction to what global exploitation looks like. |
| Link | [PassiveTotal Learn](https://www.passivetotal.org/learn) | Passive total is an amazing malicious infrastructure analysis tools. Their Learn site is all about understanding attacker infrastructure. |
| Tool | [Metasploit Framework](https://github.com/rapid7/metasploit-framework) | People are right when they say computer network attack isn't like you see in movies, but MSF is as close as it gets. |
| Book | [Hacking: The Art of Exploitation 2nd Edition](http://www.amazon.com/Hacking-Art-Exploitation-Jon-Erickson/dp/1593271441/ref=sr_1_2) | This formed the basis to me of understanding binary exploitation, though one book is only a start to this huge topic. |
| Person | [@RobertMLee](https://twitter.com/RobertMLee) - Robert M Lee | I know, another Rob Lee right? But they're both worth listening to. Rob tweets about attacker activity, especially around ISC. [His cartoon is fun too.](https://twitter.com/_LittleBobby_) |

### Development

One of the key things I believe in is the need for more security people of all stripes to be better developers. Technology changes quickly, the companies we defend move quickly, and if you're waiting for a company or open source project to build the tool you need you'll always be behind. The fact is the best DFIRs I've worked with are able to create their own solutions and even if it's just basic scripting being able to code is a game changer.

| Type | Resource | Notes |
| ---- | -------- | ----- |
| Video | [Write your own tools with python](https://www.youtube.com/watch?v=EamOtLxCweI) | Nicolle's high level introduction to Python is a whirlwind, but excellent for getting started, especially if you have some programming background. |
| Link | [CodeAcademy: Learn Python](https://www.codecademy.com/learn/python) | If you want hands on this is the place to learn Python. You'll be writing real code in minutes. |
| Tool | [Python](https://www.python.org/) | People will argue, but it's my go to. Also look at [Go](https://golang.org/). |
| Book | [Grey Hat Python](https://www.goodreads.com/book/show/5044768-gray-hat-python) | I didn't love this book, too penetration testing heavy for me, but it got the key points across. |
| Person | [@pidydx](https://www.twitter.com/pidydx) - Sean Gillespie | A passionate DFIR+Developer and one of the major non-[Google GRR](https://github.com/google/grr) developers. |

> _Aside:_ I realize I've been incredibly Python heavy. I know (and in fact personally use) other languages that are useful for DFIR. Python is simply, in my opinion, the easiest to get started and be effective with. If you have experience with something else absolutely start there. Focus on text manipulation, basic networking, accessing APIs using REST, and basic system management.

## Soft Skills

I think soft skills get overlooked in the DFIR world. We focus so deeply on esoteric system minutia we don't realize we lack to the ability to make it relevant to others or in some cases even protect ourselves. These skills are important as they enable every one of the technical skills. The other fact is these are topics the DFIR world doesn't talk a lot about. We focus on bits and bytes but we need to put more effort into the _In Real Life_ aspects of DFIR. I'm going to discuss a little of these, but honestly they all deserve posts of their own.

### Investigation Process & Analysis

My schooling with regard to investigative process came at the hands of a Marine counterintelligence sergeant and a former Atlanta police officer turned disk forensics manager. I wish I could bottle up all they taught me and sell it. The combination was incredible. I learned how to question my own biases, structure data, test theories, gather information from others, even a little about how to entice further information from the bad guys themselves. It was an amazing education.

Sadly I don't have good resources yet to teach that. I'll work on that.

### Operational Security

Being a DFIR, or security researcher of any kind, is dangerous.

- [Motherboard: Hackers Threaten Security Researchers: 'We'll Analyze Your Brain with a Bullet'](http://motherboard.vice.com/read/hackers-threaten-security-researchers-well-analyze-your-brain-with-a-bullet)
- [The Register: Security researchers face wrath of spy agencies](http://www.theregister.co.uk/2015/10/22/behind_the_headlines_apt_researchers_face_wrath_of_spy_agencies/)
- [KrebsonSecurity: Hacker Who Sent Me Heroin Faces Charges in U.S.](http://krebsonsecurity.com/2015/10/hacker-who-sent-me-heroin-faces-charges-in-u-s/)
- [Forbes: Son of Kaspersky Labs Founder Kidnapped, Lovingly](http://www.forbes.com/sites/juliaioffe/2011/04/27/son-of-kaspersky-labs-founder-kidnapped-lovingly/)

[Yeah, literally dangerous. Like kidnapped, getting shot dangerous.](https://www.youtube.com/watch?v=jZOywn1qArI) If you live in a country like the US or somewhere in Western Europe those are a lot less common. Getting compromised yourself, by criminals or an intelligence agency, can still happen anywhere. Being able to protect yourself and operate securely is critical, even above and beyond what we recommend for those we protect. Patching and being smart about what you click and where you visit are just the start, especially when DFIRs often deliberately download malware and visit the sketchy parts of the Internet. Encryption, limiting your surface area, VPNs, etc are all necessary.

### Communication

A good incident response leaves the IR team. Communication to victims. Communication to management. Communication to customers. Communication to 3rd party peers. Even communication with law enforcement. [I've talked about this before](http://sroberts.github.io/2014/09/22/crisis-comms-for-ir/) but I think it could do with a more comprehensive treatment.

### Working in a Team

[DFIR is a team sport](http://media0.giphy.com/media/reKoKNEqzn596/giphy.gif). We work in groups (more on that later) under very high stress situations where details matter and actions make a difference. Being able to delegate, be delegated to, sharing, coordinating, and doing so effectively in a time crunch is a big deal.

### Gaining Experience

One of the most important pieces to being a great DFIR is experience. Learning is great, reading and studying teaches a lot, but nothing teaches quite as much as actually doing it. There are elements of incident response that can be done at home, malware analysis is a good example. But some things, anything at scale, can only be done in the real world, working actual incidents. For this growing DFIRs need to be places where there are incidents. There are two options: work for organizations actively under attack or work for a company that consults for companies under constant attack. I cut my teeth at Symantec and Mandiant, but I'd also recommend the Big 4 consulting firms or other IR boutiques like [Optiv](https://www.optiv.com/) or [Stroz Friedenberg](http://www.strozfriedberg.com). For companies under attack... well that's almost everyone, but the [Defense Industrial Base](http://www.dhs.gov/defense-industrial-base-sector), financial, and the [Fortune100](http://fortune.com/fortune500/) are good candidates.

## T Shaped People

The last thing we'll talk about is one way to think about understanding skills as a DIFR. The lists above cover the broad range of skills DFIRs have. Is everyone a master of all these skills? Not at all (Ok, I know one person who might be but that's a total anomaly). Most DFIRs specialize in a few aspects and have less knowledge in others.

![T-Shaped People](https://docs.google.com/drawings/d/1c6xxt6JktO08HT6fIxEaCW50fVjHRvGnzbpECPMUmqk/pub?w=960&h=720)

This makes most DFIRS [_T-Shaped People_](https://en.wikipedia.org/wiki/T-shaped_skills) (see the T above now?), who have deep skills in specific areas and more limited in skills in others. [I've talked before](http://sroberts.github.io/2015/05/02/imposter-syndrome-in-dfir/#the-jack-of-all-trades-inferiority) about how I'm confident in some of my skills and less so in other skills. One of the things that makes DFIR different than many other professions is most DFIRs are jack of all trade types. I'm not excellent at malware analysis, but I can do a little bit. At the same time I'm better at Network Forensics than most.

Why is this important? Two key reasons:

- Not everyone needs to have the same skills. It's ok to have an affinity for a one skill and struggle a bit more with another.
- DFIR teams must focus on complimentary skills. If you have a team strong in memory forensics perhaps you want your next hire to be a strong malware analyst. No one person can be an expert in everything, but your team should have strength across the board.

## Conclusion
Is that all? Not in the least. There are plenty of other aspects and skills a good DFIR analyst will need. The entire field is all about learning and constantly growing. Last years nation-state technique is in every exploit kit out there. The forensics tool that used to be the best way to do things is replaced by a brand new open source tool.

## Honorable Mentions
- [Incident Response: Taking CSIRT Modeling to the Next Level](http://frodehommedal.no/presentations/first-tc-oslo-2015/#/slide-start)
- [meirwah/awesome-incident-response](https://github.com/meirwah/awesome-incident-response)
- [Starting an InfoSec Career – The Megamix – Chapters 1-3](http://tisiphone.net/2015/10/12/starting-an-infosec-career-the-megamix-chapters-1-3/)
