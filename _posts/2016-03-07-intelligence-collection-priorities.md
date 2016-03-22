---
layout: post
title: Intelligence Collection Priorities
---

![Meaningless globe picture of stuff and things..](/public/global-intel2.jpg)

One of the hardest things when starting a threat intelligence program is deciding where to start. Everyone will give you a different opinion and insist on a different approach. As for me I think the best approach is to start with the small things, the easy things, and build up from there. What's easy depends a lot on your organization but this is my general list of useful collection sources for most organizations.

## <i class="fa fa-building-o"></i> Internal Incident Data

> <i class="fa fa-quote-left"></i> Listen to your enemy, for God is talking.
~ Jewish Proverb

I love this quote and it couldn't fit this topic more perfectly. If you want to know who your enemies are look at the attacks you're already experiencing.

__The hardest part of threat intelligence isn't collecting data. That's the easy part. The hard part is deciding which data is worth collecting.__ There's no better way to focus intelligence collection than by focusing on past attacks. This comes from mining internal sources, preferably your incident management system ([certsocietegenerale/fir](https://github.com/certsocietegenerale/FIR) is a good start). _Nothing is worse than an attacker using the same resource twice_, so when you know a domain is used as C2 then keep watching that domain (and preferably the [IP addresses that have pointed to it in the past as well](https://www.passivetotal.org/)).

## <i class="fa fa-forumbee"></i> Honeypots & The Like (Emphasis on The Like)

I'll be honest... _I hate honeypots._ They're trendy right now (it's cyclical, like bell bottoms). The idea of letting a bad guy onto my network deliberately scares the heck out of me. My favorite honeypot I ever used in operation was our Active Directory server and while it was a great collection source it certainly wasn't our choice. There are some cool tools out there for it, from the classic [Honeynet Project](https://www.honeynet.org/) to [Secureworks new DCEPT project](https://github.com/secureworks/dcept) but I'm not sure I'd have the guts to run them.

What is interesting to me is the idea of using passive sources of data to enhance your detection. Want to know your most targeted users? Look at who has the most failed logins. Gathering firewall drops helps you understand what systems attackers may try to access. These passive sources of data provide internal insight that's difficult to come by otherwise.

## <i class="fa fa-file-pdf-o"></i> Vendor Reports

While opinions differ I like [long form vendor reports](http://intelreport.mandiant.com/). If you can match threat actors up with your organization's threat model you can learn a lot (don't assume everything) of what FireEye/Symantec/PaloAlto/etc knows about a given threats. The best reports also include IOCs.

Keep in mind [attackers respond differently when outed](http://files.sans.org/summit/Cyber_Threat_Intelligence_Summit_2016/PDFs/Six-Years-of-Threat-Intel-Have-We-Learning-Nothing-David-Bianco.pdf). Some plow ahead like nothing happened, some change TTPs and even exploits, others shutdown entirely. The _Use By_ date on these is often short, but that doesn't mean they're useless. In the end I think they're free, high signal reports that give insight you might not have access to otherwise.

## <i class="fa fa-users"></i> Sharing Communities

The cool kid cliques of the network defense world sharing communities are supposed to be the end all be all answer to all our security problems. [Sadly they are not](http://www.slideshare.net/AlexandrePinto10/sans-cti-summit-2016-datadriven-threat-intelligence-sharing?qid=55b556e8-5468-47d6-8a95-36d0f6a73393&v=&b=&from_search=1). __They're far from perfect. Perfect though is the enemy of good and these communities do provide a trusted place for sharing threat information.__ At their most basic these communities can be as simple as a [Slack](https://slack.com/) channel. At their most complex they're built on sharing platforms like [ThreatExchange](https://developers.facebook.com/products/threat-exchange) or [ThreatConnect](https://www.threatconnect.com/).

Getting in is the trick. These groups whether they're chat or a purpose built threat-threat platform are a mechanism for sharing trust. In most cases this trust is a proxy for real life trust, so take the time to cultivate your relationships.

## <i class="fa fa-rss"></i> Free IOC Feeds

Why are free feeds my fourth choice? They're free and all that and everyone talks about them. Well not to be blunt but they're low signal to noise and generally unfocused. Don't trust me? Ask smarter people like [Alex Pinto](https://twitter.com/alexcpsec) & [Kyle Maxwell](https://twitter.com/kylemaxwell)'s Defcon 22 Talk Measuring the IQ of your Threat Intelligence Feeds ([Slides](http://www.slideshare.net/AlexandrePinto10/defcon-22-measuring-the?qid=55b556e8-5468-47d6-8a95-36d0f6a73393&v=&b=&from_search=3) & [Video](https://www.youtube.com/watch?v=yG6QlHOAWiE)). I bet you'll agree with them.

## <i class="fa fa-money"></i> Paid IOC Feeds

<img style="float: right;" src="/public/sundae.jpg">

I know I made it last on my list but I'm not saying paid feeds are bad, in many cases they're great actually. I tend to think of it like a sundae. The ice cream is your first source, your base. The whip cream? That's when you started mining APTNotes. Rainbow sprinkles... sure I guess that's your new honeypot.

In my opinion paid feeds are your cherry on top of your threat intelligence sundae. They take a good system and make it great. Take your time, really press your vendor, and make sure you can make the most out of whatever feed you get.

## The Beginning is the End is the Beginning

So now that you've combed through your incidents, reread Kaspersky's take on the [HackingTeam's new malware](https://securelist.com/blog/research/74063/the-return-of-hackingteam-with-new-implants-for-os-x/), and all there rest what's next? Well we're quick to forget it but collection isn't the end of the intelligence cycle, it's just the beginning. The goal isn't a list of IOCs. The goal is an analyzed product that meets the needs set out in the requirements phase (you did that too right?). Which hopefully came from output from your feedback phase...
