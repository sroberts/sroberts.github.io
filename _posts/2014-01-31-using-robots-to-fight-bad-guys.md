---
layout: post
title: Using Robots to Fight Bad Guys
---

I've gone a few places and given a few talks about some of the work I've done to adapt Hubot and GitHub's Chat Ops workflow for DFIR. While it was great to get the ideas out there's a lot to deploying, using, and customizing VTR.

## How GitHub Uses Hubot: ChatOps
So [DevOps](http://en.wikipedia.org/wiki/DevOps) in general and ChatOps specifically are massive topics unto themselves and I'm not sure I'm the right person to fully address them, so here's my short version of each:

* **DevOps:** An integration of software development & systems operations to increase efficiency, consistancy, repeatability, and security.

* **ChatOps:** Doing devops by building tools that integrate with the teams chat applications.

Both of these techniques take advantage of modern development tools for rapid tool creation and integration, tools like Puppet/Chef for automation, and a data driven approach where feelings, conventional wisdom, and "thats just the way we do it" is replaced with collaboration and metrics.

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

## Writing Hubot Scripts

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