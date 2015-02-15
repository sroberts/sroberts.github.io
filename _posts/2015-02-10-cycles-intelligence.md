---
layout: post
title: Intelligence Concepts - The Intelligence Cycle
---

Yeah... this is happening. I can't talk about important intelligence concepts for security without talking about the grand daddy, the original: the Intelligence Cycle. This should be great discussion fodder for anyone who has to talk to someone who claims they're selling some form of "Threat Intelligence" product, given in most cases they seem to be using the phrase in place of the word "smart". Intelligence vs smart couldn't be farther from the truth

## [The Intelligence Cycle](https://www.cia.gov/kids-page/6-12th-grade/who-we-are-what-we-do/the-intelligence-cycle.html)

![Intelligence Cycle](/public/intelligence-cycle.png)

## In Incident Response

For the last two or so years the security industry has been all about "Threat Intelligence" with almost zero idea what the word _intelligence_ actually means. In most cases companies using the word "intelligence" are trying to say something involves an intelligent (meaning smart) concept. In many cases these are innovative and beneficial, but they aren't intelligence. This is coupled with the desire to cash in on the current "threat intelligence" trend.

Vendors are selling data feeds, management platforms, reports, and tools, but none of these are really intelligence. In every case they are a piece, and in many cases important pieces, but not a whole. The whole of threat intelligence takes tools, data sources, people, and processes dedicated to taking in all those inputs and taking them through the intelligence process.

### A Walk Through the IR Cycle

So I track a number of different groups for my own interest, so lets walk through this cycle the way I would for one of the more infamous groups out there the infamous Comment Crew, which got reported by Mandiant as APT1.

#### Direction
When I'm doing my personal research I generally have two goals:
- A general understanding of a group such as their overall goals
- Any indicators of compromise that could help me identify these groups

#### Collection

My first thought with groups like this is always figure out what else they're called. The Comment Crew was a great example of this. Comment Crew (as they were most commonly referred to in private circles) is also was referred to as "Soy Sauce", "ShadyRat", "WebC2", "GIF89a", & eventually their actual name Unit 61398. I'm stunned how often I've missed information about an actor just because I was too focused on the wrong name.

From there we have a couple common sources:

- Google: It's amazing what you can find going through articles & blog posts. You'll want to grab as many of these as you can, though watch out; the current tech media is rife with republishing all over the place, so it's not unusual to find the exact same text on half a dozen sites.
- Vendor Info: In the case of Comment Crew they have probably the most prolific single report in security community history. This of course merited a walk through with a fine tooth comb, but so did many follow on reports as well.
- From this point there's a whole new series of terms, IP addresses, URLs, CVE numbers, as well as non-technical indicators such as associated actor names, the actual unit designator of the group, etc. Each of these in turn can be collected on as well using other sources.

This to me is where tools like DomainTools and PassiveTotal are especially useful. Things like historic whois data & historic domain name resolutions can provide tons of useful data. Another big one, though $$$$, is VirusTotal, which also makes it possible to download relevant malware.

#### Processing

At this point you have a mountain of data. Seriously for this investigation it's a mountain. Processing is taking all this data and putting it into a useful format for further analysis. This is all about consistency and ease of analysis. This is one of the toughest problems in the security space right now.  

I end up processing my data into a lot of formats. For things like reports and articles I initially process them into JSON files per article. From there I push my data (note I'm saying data, not intelligence) into a number of places, including the CRITs intelligence management system and Maltego for future analysis. I also keep all my raw, but processed files around in case I need to manipulate them differently later. There are commercial options as well.

#### Analysis

Now we have the necessary collection of data processed into a consistent manner and we're ready to go back and address those original questions.

- What was this group about?
    - This is what the long form reports tell us. And for a case like this we're looking for confirmation in as many places as possible. We learn this group is about attacking military related targets, trying to gather information that will support their national defense.
- Any indicators of compromise that could help identify Comment Crew
    - At this point you (if you're playing along at home) have hundreds of indicators, IPs, hashes, malware, domain names, etc. The key for analyzing these isn't just having them, but having them in formats that can be used to support your direction. To me this means things like IPs in CSV or JSON formats that I can easily push into defensive systems or generate block lists, malware as hashes and Yara rules, etc.

That's the basic analysis process. My products for something like this generally include a couple paragraphs to answer the first requirement, likely to be continually updated, and a group of files detailing the second set of indicators. I could use on one of the major standards fro that, such as STIXX or OpenIOC, but given at this point they're both difficult to work with and not wildly well adopted I find its easier to stick with open file types like JSON, CSV, etc.

#### Dissemination

The next to last step is dissemination to stakeholders. In a case like this I'm the stakeholder, so I don't need things disseminated as this is mostly a reference set for me. In the event I was building this for someone else this is the point where I'd pass them information.

If this was being disseminated there are a few things to consider:

- Different stakeholders will need a different format of product. Engineers and analysts will want indicators in easy to work with formats (like JSON & CSV). Managers and directors will want shorter briefs, mostly in prose, and probably as PDFs. Always consider your audience in how you share your data.
- Operational Security of intelligence matters. The TLP method helps, but you have to make sure people will follow through with this. You don't want to do all this work for it to be identified by the group you're analyzing.

#### Feedback

Feedback is the simplest part of this whole cycle: Did you answer the questions posted during direction to the stakeholders satisfaction? If yes does this lead to new questions that need to be asked? If no how does this lead to generating a better question or a new series of collections?

This is a tough one to stomach. If you're the stakeholder you're answering to yourself, which makes it tough to be honest in your assessment. If the stakeholder is someone else this is their chance to judge your work. Brutal honesty with yourself throughout the process is the only answer.

## Takeaways from the Intelligence Cycle

The intelligence cycle isn't something that gets used day in and day out in DFIR work, but is becoming more and more critical to always have running in the back of your head. Whether evaluating new tools or vendors its important to understand that intelligence isn't just data, it's data that has been processed in rigorous way to ensure a balanced, well contextualized product. This is to make sure you're making good decisions, not simply following whatever data is in front of you.

## More Reading
- [Wikipedia: Intelligence Cycle](http://en.wikipedia.org/wiki/Intelligence_cycle)
- [Wikipedia: Intelligence Cycle Management](http://en.wikipedia.org/wiki/Intelligence_cycle_management)
- [Intelligence.gov: A Dynamic Process for Fueling Dynamic Solutions](http://www.intelligence.gov/mission/how-intelligence-works.html)
- [PSU.edu: Intelligence Process](https://courseware.e-education.psu.edu/courses/bootcamp/lo07/09.html)
- [CIA.gov: CIA Kent Center Occasional Papers](https://www.cia.gov/library/kent-center-occasional-papers)
