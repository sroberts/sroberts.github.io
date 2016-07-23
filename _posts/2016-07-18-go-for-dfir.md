---
layout: post
title: Golang for DFIR
description: 'An introduction to Golang for security engineers.'
---

![Golang](/public/golang.png)

One of my goals for this year was getting comfortable with a new programming language. I've been a [Python](https://www.python.org/) devotee for a long time and it's almost always gets the job done, but I wanted a little bit more. There are times Python works against you:

- __Dependency Nightmares:__ While `virtualenv` and a `requirements.txt` file work ok for developers it can often make use by non-developers or some deployment stories quite complicated.
- __Speed & Scale:__ This is a funny one. 99% of the time Python is more than fast enough and scales widely enough. Except when it doesn't. Chewing through a few hundred megabytes of logs? No big deal. Gigabytes or terabytes? Not so much. Hundreds of network connections? Sure. Hundreds of thousands or millions? You might need something more.
- __Discipline:__ Python is easy. Almost too easy sometimes. It lets you cut corners, it takes care of a lot in the background. It's a great language for getting things done but sometimes I want to learn/control/understand more. Beyond that sometimes I want software that's more than functional, I want it to be engineered. More structure, more safety, etc.

Working for company made up of largely developers there's always talk about new development tools and languages. [Rust](https://www.rust-lang.org/) and [Golang](https://golang.org) have been hotly discussed in these circles (along with [Erlang](https://www.erlang.org/)/[Elixer](http://elixir-lang.org/)/[Node](https://nodejs.org/en/)). I was considering both until I had a discussion at [ArchCon](http://www.archc0n.org/) with [Liam Randall](https://twitter.com/hectaman) who effused about how great Golang had been for his organization. Good enough for Liam is good enough for me, so I dove in.

## What is Golang?

According to the [Golang Lanugage](https://golang.org/) site:

> Golang is an open source programming language that makes it easy to build simple, reliable, and efficient software.

Go is a strongly typed, [not quite object oriented](http://spf13.com/post/is-go-object-oriented/), complied language with a syntax similar to [C](https://en.wikipedia.org/wiki/C_(programming_language)) &amp; [Python](https://www.python.org/) (with a few little quirks). It's a complied language (meaning you create an actual binary instead of just running the script like in Ruby or Python). It's garbage collected, meaning you don't have to deal with memory management (mostly), and highly concurrent, letting you run multiple threads easily. Golang was built to be a [_Google Scale_](https://talks.golang.org/2012/splash.slide) language, meaning it's meant for highly distributed large scale applications.

Ready for code? Here is [Hello World in Go](https://gist.github.com/sroberts/86b6b2b70ce0f4daa972fa9c373f72c0):
<script src="https://gist.github.com/sroberts/86b6b2b70ce0f4daa972fa9c373f72c0.js"></script>

Simple and easy.

Golang also has a highly developed set of tools that include things like managing dependencies (these get statically complied into your application so end users don't have to worry about them, just you). There are tons of libraries out there, from a well developed standard library and tons of 3rd party libraries for everything from [building websites](https://gin-gonic.github.io/gin/) to [using Yara rules](https://github.com/hillu/go-yara).

The result? You get platform specific binaries (running native, without any dependencies) that have [speed, scalablity, &amp; safety](https://www.iron.io/go-after-2-years-in-production/) along with lots useful libraries before you even start. All without having to write lower level, higher learning curve languages like C. Pretty much just what I was looking for.

It's not all upside. Golang is strict. It has right ways and wrong ways to do things and it enforces those ideas. It is slower to develop compared to Python but in many cases the complications are wroth it.

## Why use Golang for security?

I continue to think Python is the best language to start with for Security, but there are situations where you need a little bit more. For me though the first serious benefit was the compiled nature.

I was building a tool that pulled in data from various sources to use on the commandline and with [Maltego](https://www.paterva.com/web7/). Initially these started as Python scripts specifically built for Maltego but they had a couple problems:

- While they worked well enough for me they were buggy, no tests, inconsistent, and often needed me to jump in and fix mid-use.
- The configuration was highly specific to my machine. That's ok for me, but getting the same transforms setup on someone else's machine would have been hard. (Yes, we could get a TDS, but for only a handful of people that seemed like overkill.)
- Lastly as useful as it was for Maltego there were times I wanted the output on the commandline instead, to use with other scripts or tools similar to [ivanlei/threatbutt](https://github.com/ivanlei/threatbutt). Quite a change to my codebase.

The solution? Well if you haven't guessed by now I can't help you, but yes, I began rewriting the scripts in Golang. The result? A single binary that anyone can run whether on the commandline or with Maltego, feels far more consistent and runs on the commandline. It also has the upside of being a bit faster and easier to understand.

## Resources for Learning

One fascinating thing about people is how they learn in such diverse ways. Some people like reading while others prefer video. Some prefer diving right in. I'm a fan of a mixed approach, diving into real code, then backing out to learn some theory, then having references while I build. So here's a little bit of everything so you can build the best Golang curriculum for you!

### Hands on Resources

Go is a pretty straight forward language, especially if you've done a language like C, Java, or Python before. As a result one of the best ways to learn it is just diving into code itself, play with it, and see how it works. Here are the easiest ways to do that:

- Your first stop should definitely be the [A Tour of Go](https://tour.golang.org/) right on the Golang website. This walks through basic core structures with actual runable code, all within a web browser, letting you avoid Golang's somewhat tedious setup before you know it's for you.
- After you have [Golang installed](https://golang.org/doc/install) the next great hands on tool is [Exercism.io](http://exercism.io/). This project shares example problems that run live on your own machine using built in Golang tools such as `go test` to learn not just syntax, but the tool chain as well. Exercism goes a step beyond by having users collaborate on improving each other's solutions. Not to mention [the Exercism commandline tool is itself written in Golang](https://github.com/exercism/cli).

### Sites & Blogs

The web is full of resources to help you get started with Golang (almost as much as to help you catch Pokemon). Here are a few favorites:

- [Golang.org](https://golang.org/): The official site of Golang run by the project maintainers this site is a tremendous resource including software, documentation, blogs, and all kinds of other resources.
- [Learn X in Y Minutes: Golang](https://learnxinyminutes.com/docs/go/) I'm a big fan of a good cheatsheet. This is the best one I've seen for Golang. It's the perfect syntax reminder.
- [Go By Example](https://gobyexample.com/): The next step up from a cheatsheet, Go By Example has small digestable topics perfect for those moments you want to see variations on a particular pattern.
- [Komand Tech Blog](https://blog.komand.com/topic/komand-tech): Komand is a security automation suite built using Golang. They're taking an open approach and sharing what they learn, including their most recent post [Quick security wins in Golang (Part 1)](https://blog.komand.com/quick-security-wins-in-golang).
- [Awesome Go](http://awesome-go.com/): My go to place to find out "Is there a Golang project for X?". There's almost always something useful.
- [Dave Cheney's Blog](http://dave.cheney.net/): If there's a blog to start with it's Dave's. He has been writing about Golang since the beginning and has some great lessons. For newbies I recommend starting with [Resources for new Golang programmers](http://dave.cheney.net/resources-for-new-go-programmers) and [Five suggestions for setting up a Golang project](http://dave.cheney.net/2014/12/01/five-suggestions-for-setting-up-a-go-project).

### Books

- [The Go Programming Language](http://www.gopl.io/): This was where I went after the Golang Tour and I still think the best formal resource for learning Go. It's nicely paced, doesn't assume too much or too little, and covers everything in the Golang core you'll need to start building.
- [The Little Book of Go](http://openmymind.net/The-Little-Go-Book/): As far as open source books go (yep, it's 100% free as in beer) I think LBoG is as good as it gets. I keep it on my desktop and reference it often. If I were a student and the $30 price tag of GoPL scared me off this is a very close second.

### Other Resources

- The major __conference__ for Golang [GopherCon](https://www.gophercon.com/) held in Denver most summers.
- __Videos__ for many conferences  are put online by [Gopher Academy](https://www.youtube.com/channel/UCx9QVEApa5BKLw9r8cnOFEA) (Speaking of videos [GopherVids](http://gophervids.appspot.com/) is another gem.)
- __Slides__ for various conferences usually show up on [Golang talks](https://talks.golang.org/) or [github.com/golang/go GoTalks](https://github.com/golang/go/wiki/GoTalks).

## Projects to Look at!

There are tons of interesting Golang projects out there on GitHub, especially around security:

- [blackfist/deez_factors](https://github.com/blackfist/deez_factors): Identify GitHub org users without 2FA
- [Phillipmartin/gopassivedns](https://github.com/Phillipmartin/gopassivedns) - A passive DNS daemon & logging tool
- [SummitRoute/osxlockdown](https://github.com/SummitRoute/osxlockdown): A tool for securing OSX system preferences
- [mephux/kolide](https://github.com/mephux/kolide): An osquery distributed endpoint management framework
- [demisto/alfred](https://github.com/demisto/alfred): A chat bot for integrating security info into your Slack
- [sroberts/cacador](https://github.com/sroberts/cacador): And last and certainly least my own little IOC extractor

I also know there's something awesome coming out soon from [Ryan Huber](https://github.com/rawdigits) in Go. I don't want to spoil the surprise, but I'd keep an eye out.

## Companies Using Golang

Lots of security companies are making Golang part of their stack (and thus a good language to learn if you want to work for those companies):

- [CrowdStrike](https://www.crowdstrike.com/)
- [FireEye](https://www.fireeye.com/)
- [Komand](https://www.komand.com/) (as previously mentioned)
- [Kolide](https://kolide.co/)
- [Demisto](https://www.demisto.com/)

And I'm sure more are looking into it. Hopefully you will be too.
