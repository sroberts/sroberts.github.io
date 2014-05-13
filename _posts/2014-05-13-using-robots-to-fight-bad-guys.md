---
layout: post
title: Using Robots to Fight Bad Guys
---

At the end of last year I was invited few places (CentralPA Open Source, BSidesDFW, & BayThreat) and gave a talk about some of the work I've done to adapt Hubot, GitHub's friendly-ish chatbot, and GitHub's Chat Ops workflow for DFIR. While it was great to get the ideas out there's a lot to deploying, using, and customizing VTR. So this is my extended breakdown of ChatOps, Hubot, Hubot-VTR, Rhodey, and building modules in CoffeeScript.

## My Presentation
<script async class="speakerdeck-embed" data-id="d8d4ee4026280131bf6a16acd67ce186" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script>

## How GitHub Uses Hubot: ChatOps
So [DevOps](http://en.wikipedia.org/wiki/DevOps) in general and ChatOps specifically are massive topics unto themselves and I'm not sure I'm the right person to fully address them, so here's my short version of each:

* **DevOps:** An integration of software development & systems operations to increase efficiency, consistancy, repeatability, and security.

* **ChatOps:** Doing devops by building tools that integrate with the teams chat applications.

Both of these techniques take advantage of modern development tools for rapid tool creation and integration, tools like Puppet/Chef for automation, and a data driven approach where feelings, conventional wisdom, and "thats just the way we do it" is replaced with collaboration and metrics.

<img src="./public/dangerroom-full.png" alt="aspell" style="width: 700px;"/>

### Benefits of Chat
* asyncronus - searchable, read back, push notifications
* multi device - laptop, tablet, & phone
* collaborative
* a great interface to build tools around

### ChatOps & DevOps Links
* [MountainWest RubyConf 2013 ChatOps at GitHub by Jesse Newland](http://www.youtube.com/watch?v=-LxavzqLHj8)
* [toptable Tech Blog: Beginning a journey to chatops with Hubot](http://tech.toptable.co.uk/blog/2013/11/22/beginning-a-journey-to-chatops-with-hubot/)
* [FoodFightShow: ChatOps at Github With Jesse Newland](http://foodfightshow.org/2012/08/chatops-at-github-with-jesse-newland.html)

## Making Hubot a DFIR Sidekick
The idea is to make Hubot support security ops:

- open source intelligence
- network forensics
- system forensics (disk & memory)
- reverse engineering
- penetration testing & vulnerability management

## Setting Up Hubot VTR
Setting up Hubot is a simple task that's best started by looking at the [Hubot documentation](https://github.com/github/hubot/blob/master/docs/README.md) itself. Go ahead, we'll wait here.

Once you've got a basic Hubot setup you'll want to [install the VTR scripts with these directions](https://github.com/sroberts/hubot-vtr-scripts/blob/master/README.md#setup). It should be pretty painless.

## Using Hubot VTR

| Script | Description | Using It |
| ------ | ----------- | -------- |
| Code Name Generator | Generates code names for being spooky | codename |
| Geolocate IP | Identify the physical location of an IP address | geo 1.2.3.4 & geo 1.2.3.4 maxmind |
| MyWOT | Look up the reputation of a website | mywot example.com |
| Pipl | Look up OSINT on a users email address | pipl email example@example.com |
| Reputation Links | Generate links for Robtext, IP/URLVoid, etc | reputation ip 1.2.3.4 & reputation url example.com |
| Reverse DNS | Get the urls associated with an IP address | reverse dns example.com |
| Shodan | Search engine for server strings. | shodan foo |
| Short URL Expander | Take a shortened URL and find out where it redirects to. | expand url example.com |
| VirusTotal | Hash, URLs, IP Addresses | virustotal hash abcd1234, virustotal ip 1.2.3.4, & virustotal ip example.com |
| Yara | Generates template for creating Yara rules. | yara-template |

## Writing Hubot Scripts
Hubot scripts are written in CoffeeScript. CoffeeScript is basically a higher level language that compiles to JavaScript and is then interpreted by Node.js.

```coffeescript
# Description:
#   Get domains associated with a specific IP Address based on http://hackertarget.com/reverse-dns-lookup/
#
# Dependencies:
#   None
#
# Configuration:
#   None
#
# Commands:
#   hubot reverse dns <ip> - Gets domains associated with an IP
#
# Author:
#   Scott J Roberts - @sroberts

api_url = "http://api.hackertarget.com"

module.exports = (robot) ->
  robot.respond /reverse dns (.*)/i, (msg) ->
    ip = msg.match[1].toLowerCase()
    robot.http(api_url + "/reversedns/?q=#{ip}")
      .get() (err, res, body) ->
        if res.statusCode is 200
          msg.send "Reverse DNS: #{body}"
        else
          msg.send "Error: Couldn't access #{api_url}."
```

There are a few major parts of any Hubot script:

* **Documentation:** This is actually quite important given that this documentation is passed along into chat when people ask for help.  It's important that this be descriptive and complete.
* **The Respond or Hear Method:** Hubot can listen for anyone mentioning a specific phrase (```robot.hear```) addressed to anyone, or wait to be addressed directly (```robot.respond```). In either case this is followed with a regular expression detailing what statement to listen for. Anything in ```()``` is saved and can be used in the method body.  
* **The Method Body:** This is where the bulk of the work happens. Call a 3rd party API, manipulate text, anything you can think of that you can do in CoffeeScript. In nearly every case the method body has one or more ```msg.send "Foo"``` statement, which has Hubot respond back to the chat.

These are the simpliest requirements, but of course there are many optional patterns as well. CoffeeScript tends to be fairly simple, so the best way to pick things up is usually just browsing through open source scripts.

## Rhodey - VTR Rest Service

## My Setup

## Things to Build
* VTR Helper Library
* ["The List"](https://gist.github.com/sroberts/f9ea3a774c585c094f15)
* Other's ideas...

## Resources
* [Hubot](http://hubot.github.com) & [Hubot Source](https://github.com/github/hubot)
* [Hubot VTR Scripts](https://github.com/sroberts/hubot-vtr-scripts) & [Hubot VTR Rhodey](https://github.com/sroberts/hubot-vtr-rhodey)
* [Chatops @ GitHub](www.youtube.com/watch?v=NST3u-GjjFw) - [Jesse Newland](https://twitter.com/jnewland)
* [Programming Butler: Hubot Scripts Explained](theprogrammingbutler.com/blog/archives/2011/10/28/hubot-scripts-explained/) - [Jon Hoyt](https://twitter.com/jonmagic)
* [Code School: Learn Coffeescript](https://www.codeschool.com/courses/coffeescript)