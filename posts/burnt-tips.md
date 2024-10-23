---
layout: post
title: Burnt TIPs
date: 2021-07-31T12:00:00.00Z
tags:
  - intelligence
  - open-source
---
![Pork Belly Pseudo Burnt Ends by Ryan Kovar](/images/uploads/porkbellyburnends.jpg "Pork Belly Pseudo Burnt Ends by Ryan Kovar")

> Special Thanks to [Ryan Kovar](https://www.twitter.com/meansec) for the photo & delicious dinner.

This is going to be one of those highly metaphor-driven posts I’ve done before (like using Hamilton in [Waiting vs Passivity in DFIR](https://sroberts.io/posts/2016-12-10-waiting-vs-passivity-in-dfir/)). Bail out now or prepare to discuss where threat intel and American BBQ run into each other!

What you call something matters in sharing it with others and framing intelligence programs. And lunch orders… 

## 🍖 BBQ: Burnt Ends

I don’t know the _real_ story of burnt ends. I doubt anyone does. The generally believed/logical sounding/possibly apocryphal version goes something like this:

> Busy BBQ stands in the Texas/Kansas City tradition would slice brisket for sandwiches and plates. Briskets are not uniform (because 🐄 are not uniform), which means there would be one-off bits, the _ends_, that would cook at a different temperature (meaning they could be inconsistently done), hard to cut into uniform slices, and often extra fatty. These scraps would accumulate at the end of the shift as unsellable. Hungry pit masters, knowing you don’t eat your supply, would doctor these extra bits for their own meals. Throw them under extra smoke, crisp them, render some fat, and roll them in extra bbq sauce. These became known as burnt ends.

Here’s the “problem”: They were delicious! While not for everyone these extra smoky fatty scraps, though inconsistent, can often produce some of the best bites! Go to a good bbq spot now and they’re some of the hardest pieces to get because they’re such a small part of the brisket. What used to be scraps the kitchen staff made edible are now one of the most sought after orders and often among the most expensive.

### 🍖 BBQ: So what?

Seeing that customers wanted the once leftover ends enterprising pit masters started “making ends”. After all the idea is simple: extra fatty flavorful pieces that get a regular smoke followed by a “hard smoke” (smoking at a higher temperature to render some of that fat and impart more smoke flavor) and then roll the ends in BBQ sauce. While making more briskets to trim for burnt ends is cost-prohibitive a [pork belly](https://www.meatchurch.com/blogs/recipes/pork-belly-burnt-ends) (the bacon part of a pig) or [brisket flat](https://www.meatchurch.com/blogs/recipes/brisket-burnt-ends) is far cheaper, cooks more consistently, and has the same characteristics as brisket trimmings.

Now it’s common to get burnt ends all the time… but they’re not traditional burnt ends! And they’re delicious!

But I’d argue they aren’t burnt ends. They’re an invention trying to do the same thing. Is that bad? No! It’s innovative and delicious and I support it, but I’d argue we shouldn’t call them burnt ends (since they’re not, they’re not trimmed and double smoked nor are they ends). The definition matters, they deserve a name of their own.

Okay, but this isn’t a bbq blog, so how does this relate to Cyber Threat Intelligence.

## 💻 CTI: Threat Intelligence Platforms

About 10 years ago a new class of system showed up on the scene to try to help analysts understand threats they were facing. While SIEMs were about logs in your environment these systems, dubbed Threat Intelligence Platforms (TIPs), were about trying to understand threats that may or may not be in your environment (hopefully not). Before these systems most organizations built ad-hoc systems to capture the same data. A group I worked had a heavily templated [DokuWiki](https://www.dokuwiki.org), most people used spreadsheets of some kind, but at some point specialized systems started showing up.

> I’m not referencing specific products here; insert your own where/if you feel appropriate.

Now here’s where we get to the rub (not a bbq reference): No one agreed what problem these were solving, so each one took their own approach.

- Some are purpose built and some pivoted from other uses like network reconnaissance or even generalized intelligence analysis.
- Some focus on storing the data from those spreadsheets in domain specific structured formats, some focus on manipulating and moving around active information. 
- Some are highly automated and just output the data an algorithm determines the user wants, some are highly analyst-driven and output the data the analysts ask for. 
- Some output data to ingest into other systems like SIEMs while others output pretty pictures and a few even try to output written narratives.

Which was the right one? Well, as any analyst will tell you, it depends. In most cases there were two major camps all those ideas above could get sorted into:

| | |
| - | - |
| **Threat Data Libraries** | The replacements for the spreadsheets, focused comprehensive collection of indicators of compromise (IOCS). These were basically highly specialized content management systems with automation to do enrichment and transport of atomic IOCs (IPs, Hashes, File Names, URLs, etc.).  |
| **Analyst Workbenches** | Tools made for taking a subset of total intelligence data, manipulating it, and developing new intelligence. These are often very manual systems aimed at professional analysts. They generally have very evolved user interfaces aimed at efficiently presenting data and doing bespoke manipulations. |

What about a hybrid? There are very few that can legitimately claim this, but most of them want to be. If you find a tool that can do both for you that’s excellent, but I’m going to treat them as distinct since I’ve almost used both together.

> **Where are the Open-Source Analyst Workbenches?** In short, there aren’t really any. Some folks will argue some open source comprehensive tools (the ones that try to be both functions) do this, but I’d argue most of them visualize IOCs but don’t really provide a good facility to manipulate them. [Maltego](https://www.maltego.com), while a prosumer (I.e., not enterprise $$$ but also not free) tool, is about as close as it gets.

### 💻 CTI: So what?

The problem is both of these types of tools called TIPs. But, are they? In the current nomenclature I would answer yes… but that’s the problem. While beef scraps and cubed pork belly aren’t both burnt ends in the same way I would argue Threat Data Libraries and Analyst Workbenches aren’t both TIPs. And in both examples I want both options in my life. Instead we confuse people by calling them the same thing.

Does this realization change the world? Do I think project owners are going to read my post, 🤦‍♂️, and change their nomenclature to split these tools up? Of course not. But as analysts and intelligence program managers we need to think critically about the tools we use (whether open-source tools or paid tools because remember “Open-Source is only free if your time is worth nothing”) and ask a few questions.

#### Questions To Ask Adding New Intelligence Tools

- What problem does this tool solve?
- Does my team have that problem?
- Are we in a place to fully leverage this tool effectively?
- Do we know what our inputs are?
  - Does this tool help us leverage those inputs?
  - Does it read the kind of data we have?
  - Does it present an input style, like a query language or interface, that analysts want?
- Do we know what our outputs can be?
  - Does this tool help us create the products our customers need?
  - Does it write the kind of data we need?
  - Does it present an output style, like export formats, that analysts want?
- Does it integrate with the other tools we need?

Is that it? Absolutely not, but it’s a good start. The key is realizing that a TIP (whether a workbench, a library, or hybrid) is a system that works with both other systems.

## 🏁 In the End

Whether it’s a TIP or a workbench or a library we don’t use our tools in a vacuum and ultimately are meant to enhance an analyst's effort. The key is how a tool integrates into your environment, your team, and your data. It's a worthwhile exercise to look at your tools and figure out how to get the most out of all of them!

And how about we all stop using generalize terms that don’t accurately describe things. Now we just need a better name for those pork belly bits! And I need some dinner!
