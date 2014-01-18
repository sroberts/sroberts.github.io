---
layout: post
title: My Favoirte Open Source Security Tools
---
So working at [GitHub](http://github.com) it's no surprise I believe in and use a lot of open source software. I think especially for security this makes sense, for a number of reasons:
* We need tools we can trust, so transparancy is key
* We need tools we can modify, since we often need things that don't exist
* We need tools that are cross platform

And the list goes on. I try to support these projects, with code, with feedback, with use, and sometimes, with praise. So here are a few of my favorite open source security tools:

## [Google's Rapid Response](https://code.google.com/p/grr/)
Ok, #realtalk: This is an open source version of [Mandiant](http://www.mandiant.com)/[FireEye](http://www.fireeye.com)'s MIR incident response platform. The idea is systems have an agent that reports to a server. The server can then set up jobs to look across an individual system, a group, or an entire population for a specific indicator of compromise, individual file, or many other forensic artifacts. 

Given the expense of MIR or similar systems like Encase Enterprise it's truely astonishing the amount of effort the Google team working on GRR has put in, and it's a huge benefit to the community that they've released it. You can find more information on their [user mailing](https://groups.google.com/forum/#!forum/grr-users) list and [Google Code](https://code.google.com/p/grr/) site. As a side note I made a [fork on GitHub](https://github.com/grr-hackers/grr) to encourage even more open source collaboration. I'm really intersted in talking to folks who want to work on this.

## [AOL's Moloch](https://github.com/aol/moloch)
So if GIR is an open source version of MIR the Moloch is an open source version of EMC/RSA/Netwitness's [Netwitness Investigator](http://www.emc.com/security/rsa-netwitness.htm) full content monitoring tool. Put together by the fine folks at AOL Moloch helps you capture and hunt in network traffic.

## [FordropWeb](https://github.com/berggren/fordropweb)
So this project hasn't gotten a lot of love lately, but it's hugely interesting to me. There aren't a lot of tools that try to make it easier to collaborate on forensic investigations, in fact most seem hell bent on the exact opposite. I'd love to see more work on this tool, and will be setting it up at home soon.

## [OSX Auditor](https://github.com/jipegit/OSXAuditor)
I'm an OSX user and work with a lot of OSX users. OSX security tools are few and far between, so OSX Auditor is a great tool. OSX Auditor checks in on your important system files, makes sure they stay unchanged, and alerts you to strange changes. I'm especially interested in this to do a "before and after" look at systems, such as if you had a laptop taken at customs. Fills a limited niche.

## [PyIOC](https://github.com/jeffbryner/pyioc)
Exchanging information about threats is a shockingly complex task. Mandiant (yeah, they're back) released an XML based format for sharing information with their [OpenIOC](http://www.openioc.org) indicator format. Now I hate XML, but PyIOC attempts ot make it easier to work with OpenIOC in a programtic way. Super useful for automatic generation of signatures/rules or other detection formats.

## [Buffer's Thug](https://github.com/buffer/thug) - Python low-interaction honey client
## [Cuckoo Sandbox](https://github.com/cuckoobox/cuckoo) - Cuckoo Sandbox main repository
