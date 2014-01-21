---
layout: post
title: Using Robots to Fight Bad Guys
---

I've gone a few places and given a few talks about some of the work I've done to adapt Hubot and GitHub's Chat Ops workflow for DFIR. While it was great to get the ideas out there's a lot to deploying, using, and customizing VTR.

## How GitHub Uses Hubot: ChatOps
http://tech.toptable.co.uk/blog/2013/11/22/beginning-a-journey-to-chatops-with-hubot/

## Making Hubot a DFIR Sidekick
The idea is to make Hubot support security ops:
- open source intelligence
- network forensics
- system forensics (disk & memory)
- reverse engineering
- penetration testing & vulnerability management

## Setting Up Hubot VTR

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
* Hubot
* Hubot VTR Scripts & Hubot VTR Rhodey
* Chatops at github - jesse newland
* programming butler: hubot scripts explained
* code school: learn coffeescript