---
layout: post
title: A brief introduction to osquery
---

I admit it... I'm a fanboy. Straight up [osquery](http://osquery.io) fanboy.

Oh... what is osquery you ask? Good question there sport.

> osquery allows you to easily ask questions about your Linux and OSX infrastructure. Whether your goal is intrusion detection, infrastructure reliability, or compliance, osquery gives you the ability to empower and inform a broad set of organizations within your company.

Or so says Facebook at least. For my money __osquery is the most effective way available to monitor an OSX or Linux host for security__. Not bad eh?

The big question everyone asks though is how do you get started with osquery, so without further ado:

# Getting Started with osquery

All in 3 easy steps... followed by 2 hard ones.

## Step 1: Install osquery

This one is pretty simple. Just follow these [handy instructions](https://osquery.io/downloads/).

__OSX Side Note:__ _If you're on OSX and a fan of Homebrew (as I am) you'll actually want to skip Homebrew this time and install the package directly. Homebrew gets wierd about running things as root later on, and that'll be a pain. Safe yourself the pain._

## Step 2: Learning osqueryi

osquery provides two main interfaces to the user: osqueryi and osqueryd (we'll get to osqueryd in another post). osqueryi is a REPL (Read-Evaluate-Print Loop) similar to `$ irb` or `$ python`. This lets you input a command and get back an immediate response. We can use this for a few things:

- One off, spot checking of specific system attributes.
- Developing new queries.
- Learning your way around osquery.

So lets give it a try. Get started simply by typing `osqueryi` at your terminal.

## Want to Learn More?

So do I. There's a lot to osquery. It's not a solution, it's a framework. On one hand that makes it customiziable, on the other tha means many parts of using it are _left to the user_.

<iframe src="http://sroberts.github.io/bsidesdfw2015-slides/slides.html#1" style="border:none" width=533px></iframe>

I recommend you don't fire until you're within 40,000 kilometers. Worf, It's better than music. It's jazz. You enjoyed that. Then maybe you should consider this: if anything happens to them, Starfleet is going to want a full investigation. Maybe if we felt any human loss as keenly as we feel one of those close to us, human history would be far less bloody.
