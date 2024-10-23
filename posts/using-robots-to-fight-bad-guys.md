---
title: "Using Robots to Fight Bad\_Guys"
date: 2014-05-14T05:00:00.000Z
tags:
  - development
  - intelligence
  - network-defense
---

At the end of last year I was invited few places (CentralPA Open Source, [BSidesDFW](http://www.securitybsides.com/w/page/60987881/BSidesDFW), & [BayThreat](http://www.baythreat.org/)) and gave a talk about some of the work I’ve done to adapt Hubot, GitHub’s friendly-ish chatbot, and GitHub’s Chat Ops workflow for DFIR. While it was great to get the ideas out there’s a lot to deploying, using, and customizing VTR. So this is my extended breakdown of [ChatOps](http://www.reddit.com/r/chatops/), [Hubot](https://hubot.github.com/), [Hubot-VTR](https://github.com/sroberts/hubot-vtr-scripts), and building modules in [CoffeeScript](http://coffeescript.org/).

### My Presentation

[Building Your Own DFIR Sidekick](https://speakerdeck.com/sroberts/building-your-own-dfir-sidekick-threads-edition)

### How GitHub Uses Hubot: ChatOps

So [DevOps](http://en.wikipedia.org/wiki/DevOps) in general and ChatOps specifically are massive topics unto themselves and I’m not sure I’m the right person to fully address them, so here’s my short version of each:

|             |                                                                                                                               |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **DevOps**  | An integration of software development & systems operations to increase efficiency, consistency, repeatability, and security. |
| **ChatOps** | Doing devops by building tools that integrate with the teams chat applications.                                               |

Both of these techniques take advantage of modern development tools for rapid tool creation and integration, tools like [Puppet](http://puppetlabs.com/)/[Chef](http://www.getchef.com/chef/) for automation, and a data driven approach where feelings, conventional wisdom, and “that’s just the way we do it” is replaced with collaboration and metrics.

![](https://cdn-images-1.medium.com/max/800/0*w_QQJaGF2Dywjm0U.png)

### Benefits of Chat

|                         |                                                               |
| ----------------------- | ------------------------------------------------------------- |
| **asynchronous:**       | searchable, read back, push notifications                     |
| **multi device:**       | laptop, tablet, & phone                                       |
| **collaborative**       | it seems obvious but issuing commands together is big         |
| **flexible interface:** | an extensible and easy to use interface to build tools around |

The idea is to make Hubot support security ops:

- open source intelligence
- network forensics
- system forensics (disk & memory)
- reverse engineering
- penetration testing & vulnerability management

### Setting Up Hubot VTR

Setting up Hubot is a simple task that’s best started by looking at the [Hubot documentation](https://github.com/github/hubot/blob/master/docs/index.md) itself. Go ahead, we’ll wait here.

Once you’ve got a basic Hubot setup you’ll want to [install the VTR scripts with these directions](https://github.com/sroberts/hubot-vtr-scripts/blob/master/README.md#setup). It should be pretty painless.

### Using Hubot VTR

#### **Code Name Generator**

Generates code names for being spooky

```
hubot codename
```

#### **Geolocate IP**

Identify the physical location of an IP address

```
hubot geo 1.2.3.4
hubot geo 1.2.3.4 maxmind
```

#### MyWOT

Look up the reputation of a website

```
hubot mywot example.com
```

#### Pipl

Look up OSINT on a users email address

```
hubot pipl email example@example.com
```

#### Reputation Links

Generate links for Robtext, IP/URLVoid, etc

```
hubot reputation ip 1.2.3.4
hubot reputation url example.com
```

#### Reverse DNS

Get the urls associated with an IP address

```
hubot reverse dns example.com
```

#### Shodan

Search engine for server strings.

```
hubot shodan foo
```

#### Short URL Expander

Take a shortened URL and find out where it redirects to.

```
hubot expand url example.com
```

#### VirusTotal

Hash, URLs, IP Addresses

```
hubot virustotal hash abcd1234
hubot virustotal ip 1.2.3.4
hubot virustotal ip example.com
```

#### Yara

Generates template for creating Yara rules.

```
hubot yara-template
```

These all require addressing Hubot directly, either by using the bots given name or an alias. So for me that would be hubot Shodan openssh or ! yara-template. Both your Hubots name and alias can be configured during setup.

### Writing Hubot Scripts

Hubot scripts are written in CoffeeScript. CoffeeScript is basically a higher level language that compiles to JavaScript and is then interpreted by Node.js.

There are a few major parts of any Hubot script:

- **Documentation:** This is actually quite important given that this documentation is passed along into chat when people ask for help. It’s important that this be descriptive and complete.
- **The Respond or Hear Method:** Hubot can listen for anyone mentioning a specific phrase (robot.hear) addressed to anyone, or wait to be addressed directly (robot.respond). In either case this is followed with a regular expression detailing what statement to listen for. Anything in () is saved and can be used in the method body.
- **The Method Body:** This is where the bulk of the work happens. Call a 3rd party API, manipulate text, anything you can think of that you can do in CoffeeScript. In nearly every case the method body has one or more msg.send "Foo" statement, which has Hubot respond back to the chat.

These are the simplest requirements, but of course there are many optional patterns as well. CoffeeScript tends to be fairly simple, so the best way to pick things up is usually just browsing through open source scripts.

### My Setup

I currently run two separate Hubots with different adapters and environments:

- **Development:** On my laptop I have a Hubot running with the terminal adapter. Basically it just spawns a shell that acts as chat directly with Hubot. It’s not easy to use, but it’s fast for testing without having to redeploy, just restart the server. This system has no memory (Redis database), just a brain ([Node.js](http://nodejs.org/) server).
- **Production:** I have a shared chat room with some other DFIR types and we have a shared Hubot. This Hubot is deployed onto [Heroku](https://www.heroku.com/), a single dyno system, and has a RedisToGo memory. We use [Slack](https://slack.com/) as our chat server, we it, and their [Hubot integration](https://github.com/tinyspeck/hubot-slack) is excellent. This is actually a pretty ideal setup, and definitely what I’d recommend for a first deploy.

### Things to Build

Take a look at [“The List”](https://gist.github.com/sroberts/f9ea3a774c585c094f15). There are endless possibilities, new modules, new integrations. My current goals revolve around [Yara](https://github.com/plusvic/yara), including automating signature generation. That said make this what will help you, and pull requests are always welcome.

### ChatOps Resources

#### Hubot & Hubot VTR

- [Hubot](http://hubot.github.com/) & [Hubot Source](https://github.com/github/hubot)
- [Hubot VTR Scripts](https://github.com/sroberts/hubot-vtr-scripts) & [Hubot VTR Rhodey](https://github.com/sroberts/hubot-vtr-rhodey)
- [Chatops @ GitHub](http://www.youtube.com/watch?v=NST3u-GjjFw) — [Jesse Newland](https://twitter.com/jnewland)
- [Programming Butler: Hubot Scripts Explained](http://theprogrammingbutler.com/blog/archives/2011/10/28/hubot-scripts-explained/) — [Jon Hoyt](https://twitter.com/jonmagic)
- [Code School: Learn Coffeescript](https://www.codeschool.com/courses/coffeescript)

#### ChatOps & DevOps

- [MountainWest RubyConf 2013 ChatOps at GitHub by Jesse Newland](http://www.youtube.com/watch?v=-LxavzqLHj8)
- [toptable Tech Blog: Beginning a journey to chatops with Hubot](http://tech.toptable.co.uk/blog/2013/11/22/beginning-a-journey-to-chatops-with-hubot/)
- [FoodFightShow: ChatOps at Github With Jesse Newland](http://foodfightshow.org/2012/08/chatops-at-github-with-jesse-newland.html)
