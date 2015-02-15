---
layout: post
title: Intelligence Concepts - The Intelligence Cycle
---

I can't talk about important intelligence concepts for security without talking about the grand daddy, the original: the Intelligence Cycle. This should be great discussion fodder for anyone who has to talk to someone who claims they're selling some form of "Threat Intelligence" product, given in most cases they seem to be using the phrase in place of the word "smart". Intelligence vs smart couldn't be farther from the truth.

## [The Intelligence Cycle](https://www.cia.gov/kids-page/6-12th-grade/who-we-are-what-we-do/the-intelligence-cycle.html)

![Intelligence Cycle](/public/intelligence-cycle.png)

That's it. Six steps described in six sentences, all pretty straight forward and clear. So how could this get so wildly misconstrued?

## In Incident Response

For the last two or so years the security industry has been all about "Threat Intelligence" with almost no idea what the word _intelligence_ actually means. In most cases companies using the word _intelligence_ are trying to say something involves an intelligent concept. In many cases these are innovative and beneficial, but they aren't intelligence. This is coupled with the desire to cash in on the current (and ambigious) _threat intelligence_ trend and thus everything is _intelligence_.

Vendors are selling data feeds, management platforms, actor reports, vulnerability centric reports, and tools, but none of these are really intelligence. In every case they are a piece, and in many cases important pieces, but not a whole. The whole of threat intelligence takes tools, data sources, people, and processes dedicated to collecting in all those inputs and contextualizing them by working through the intelligence process.

### A Walk Through the Intelligence Cycle

I track a number of different groups for my own interest and work through this cycle often. In this case we're going to walk through this cycle the way I would for one of the more infamous groups out there; the infamous Comment Crew aka APT1.

#### Direction
__First we have to set the paramaters of what questions we're trying to answer.__ When I'm doing my personal research I generally have two goals:

- A general understanding of a group such as their overall goals.
- Any indicators of compromise that could help me identify this group.

#### Collection

__Collection is the process of gathering as much information as you can that can help answer the questions posed in direction.__ My first thought with groups like this is come up with a series of search terms or known datapoint to start our collection of of.

> __Aside:__ A tricky aspects of finding search term is determining what a group is called. Comment Crew (as they were most commonly referred to in private circles) is also was referred to as _Soy Sauce_, _ShadyRat_, _WebC2_, _GIF89a_, _APT1_, _Comment Panda_, and eventually their actual name _Unit 61398_. I'm stunned how often I've missed information about an actor just because I was too focused on the wrong name.

From there we have a couple common sources:

- Google
    - It's amazing what you can find going through articles & blog posts. You'll want to grab as many of these as you can, though watch out; the current tech media is rife with republishing all over the place.
- Vendor Information
    - In the case of Comment Crew they were the focus of the most prolific single vendor report in security community history. This of course merited a walk through with a fine tooth comb, but so did many follow on reports as well.
- Re-Analyzing Information
    - From this point there's a whole new series indicators of compromise as well as non-technical indicators such as associated actor names, the actual unit designator of the group, etc. Each of these in turn can be collected on as well using other sources. This is where tools like DomainTools, VirusTotal, and PassiveTotal are especially useful.

The collection process continues until exhausted, either based on content or on time.

#### Processing

At this point you have a mountain of data. __Processing is taking all this data and putting it into useful formats for further analysis.__ This is all about consistency and ease of analysis. This is one of the toughest problems in the security space right now and has resulted in a lot of competing solutions (CRITs, MISP, ThreatConnect, ThreatQuotient, and dozens of home grown systems).  

I end up processing my data into a lot of formats. For things like reports and articles I initially process them into JSON files per article. From there I push my data (___Note: I'm saying data, not intelligence yet___) into a number of places, including the CRITs intelligence management system and Maltego for future analysis. I also keep all my raw, but processed files around in case I need to manipulate them differently later.

#### Analysis

__Now we have the necessary collection of data processed into a consistent manner and we're ready to go back and address those original questions.__

- A general understanding of a group such as their overall goals?
    - This is what the long form reports tell us. And for a case like this we're looking for confirmation in as many places as possible. We learn this group is about attacking military related targets, trying to gather information that will support their national defense.
- Any indicators of compromise that could help identify Comment Crew
    - At this point you have hundreds of indicators, IPs, hashes, malware, domain names, etc. The key for analyzing these isn't just having them, but having them in formats that can be used to support your direction. This means formatting (we'll get into that in dissemination) but also deconfliction, making sure that you understand the context of the indicators you have.

> __Aside on Deconfliction:__ Plenty of pieces of malware beacon to well known sites/IPs to make sure they're connected to the Internet. You don't want to report 8.8.4.4 (Google DNS) is a malicious IP. At the same time identifying a malware characteristic that is found in 100% of a groups malware is great, unless it's also found in 100% of all PE files (```MZ```).

That's the basic analysis process. My products for something like this generally include a couple paragraphs to answer the first requirement, likely to be continually updated, and a group of files detailing the second set of indicators. I could use on one of the major standards for that, such as STIXX or OpenIOC, but given at this point they're both difficult to work with and not wildly well adopted I find its easier to stick with open file types like Markdown, JSON, CSV, etc.

#### Dissemination

The next to last step is dissemination to stakeholders. In a case like this I'm the stakeholder, so I don't need things disseminated as this is mostly a reference set for me. __In the event I was building this for someone else this is the point where I'd pass them information.__

If this was being disseminated there are a few things to consider:

- Different stakeholders will need a different format of product
    - Engineers and analysts will want indicators in easy to work with formats (like JSON & CSV). Managers and directors will want shorter briefs, mostly in prose, and probably as PDFs. Always consider your audience in how you share your data.
- Operational security of intelligence matters
    - The TLP method helps, but you have to make sure people will follow through with this. You don't want to do all this work for it to be identified by the group you're analyzing.

#### Feedback

Feedback is the simplest part of this whole cycle: __Did you answer the questions posted during direction to the stakeholders satisfaction?__ If yes does this lead to new questions that need to be asked? If no how does this lead to generating a better question or a new series of collections?

This is a tough one to stomach. If you're the stakeholder you're answering to yourself, which makes it difficult to be honest in your assessment. If the stakeholder is someone else this is their chance to judge your work. Brutal honesty with yourself throughout the process is the only answer.

## Takeaways from the Intelligence Cycle

The intelligence cycle isn't something that gets used day in and day out in DFIR work, but is becoming more and more critical to always have running in the back of your head. Whether evaluating new tools or vendors its important to understand that intelligence isn't just data, it's data that has been processed in rigorous way to ensure a balanced, well contextualized product. This is to make sure you're making good decisions, not simply following whatever data is in front of you.

## More Reading
- [Wikipedia: Intelligence Cycle](http://en.wikipedia.org/wiki/Intelligence_cycle)
- [Wikipedia: Intelligence Cycle Management](http://en.wikipedia.org/wiki/Intelligence_cycle_management)
- [Intelligence.gov: A Dynamic Process for Fueling Dynamic Solutions](http://www.intelligence.gov/mission/how-intelligence-works.html)
- [PSU.edu: Intelligence Process](https://courseware.e-education.psu.edu/courses/bootcamp/lo07/09.html)
- [CIA.gov: CIA Kent Center Occasional Papers](https://www.cia.gov/library/kent-center-occasional-papers)
