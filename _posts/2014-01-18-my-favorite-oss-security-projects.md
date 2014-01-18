---
layout: post
title: My Favoirte Open Source Security Tools
---
So working at [GitHub](http://github.com) it's no surprise I believe in and use a lot of open source software. I think especially for security this makes sense, for a number of reasons:

* We need tools we can trust, so transparancy is key
* We need tools we can modify, since we often need things that don't exist
* We need tools that are cross platform

And the list goes on. I try to support these projects, with code, with feedback, with use, and sometimes, with praise. So, in sort of a weird security ["Oprah like" favorite things list](http://i.imgur.com/nQAOEmT.gif) here are a few of my favorite open source security tools:

## [Google's Rapid Response](https://code.google.com/p/grr/)
Ok, #realtalk: This is an open source version of [Mandiant](http://www.mandiant.com)/[FireEye](http://www.fireeye.com)'s MIR incident response platform. The idea is systems have an agent that reports to a server. The server can then set up jobs to look across an individual system, a group, or an entire population for a specific indicator of compromise, individual file, or many other forensic artifacts. 

Given the expense of MIR or similar systems like Encase Enterprise it's truly astonishing the amount of effort the Google team working on GRR has put in, and it's a huge benefit to the community that they've released it. You can find more information on their [user mailing](https://groups.google.com/forum/#!forum/grr-users) list and [Google Code](https://code.google.com/p/grr/) site. As a side note I made a [fork on GitHub](https://github.com/grr-hackers/grr) to encourage even more open source collaboration. I'm really intersted in talking to folks who want to work on this.

## [AOL's Moloch](https://github.com/aol/moloch)
So if GIR is an open source version of MIR the Moloch is an open source version of EMC/RSA/Netwitness's [Netwitness Investigator](http://www.emc.com/security/rsa-netwitness.htm) full content monitoring tool. Put together by the fine folks at AOL Moloch helps you capture and hunt in network traffic.

## [Etsy & Facebook's MIDAS](https://github.com/etsy/midas)
Oh the fine folks from Etsy & Facebook gave us a gift. MIDAS, the Mac Intrusion Detection Analysis System, is a framework for building host level detection of compromises specifically for OSX. It allows building complex detection routines in Python, then provides the structure to run, store, and report on them. I've done a bit of work with this and see amazing potential long term. 

## [FordropWeb](https://github.com/berggren/fordropweb)
So this project hasn't gotten a lot of love lately, but it's hugely interesting to me. There aren't a lot of tools that try to make it easier to collaborate on forensic investigations, in fact most seem hell bent on the exact opposite. I'd love to see more work on this tool, and will be setting it up at home soon.

## [Buffer's Thug](https://github.com/buffer/thug)
So you know that time you have to go investigate a nasty webpage? There are plenty of options: fire up a VM, try to use a stripped down browser, curl the site. All of these give away some amount of information that you're profiling, and may miss things. Thug seeks to fix this, by providing a safe (not a real web browser) method that still correctly emulates what a browser would look like (such as an IE7 user agent string instead of a curl user agent string). Thug makes it safe, easy, and quick to do this type of analysis.

## [Cuckoo Sandbox](https://github.com/cuckoobox/cuckoo)
Cuckoo Sandbox is easily one of the most mature open source security tools available, and the team behind it should be appluaded for that. A malware analysis system, Cuckoo runs malware through a VM, captures system changes, web traffic, and other malware relevent activity and shares it with the analyst. Having just gone [1.0](http://cuckoosandbox.org/2014-01-09-cuckoo-sandbox-10.html) they've added tons of features, improved stability, and put this tool on par with more expensive commercial malware systems. If you work with Windows based malware, this system should be in your arsneal. 
