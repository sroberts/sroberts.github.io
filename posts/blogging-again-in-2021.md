---
layout: post
title: Blogging Again in 2021
date: 2021-06-20T15:15:46.398Z
tags:
  - meta
  - open-source
  - development
---
I’m back! That means getting things back in order. When I was last writing actively I was using [Medium](https://sroberts.medium.com)… which was pretty miserable. Medium was great for ease of use with a decent writing interface and app as well as excellent reader acquisition. Unfortunately the upsides had worse downsides. Formatting was limited (no tables?!) and everything was like when I used [Jekyll](https://jekyllrb.com) but sort of weird. Then came the lock-in/paywalls and general lack of openness. 👎

## Goals

First thing to think about is what I was really looking for. I’ll be honest, my first blog was really just started because everyone at GitHub had a Jekyll based blog, so I wanted one too (bandwagon!). At this point between my past and expected future writing I have some requirements.

* Open Source Based
* Super Fast
* Markdown Driven
* Easy, Minimalist Themes
* Usable on Mobile
* Privacy Protecting Analytics

There’s some other nice to haves like easy to setup search, being relatively cheap, but not so much.

## Move back to Open Source

While I wasn’t writing for the last two years I did cut things over to a new open source platform based on [Hugo](https://gohugo.io), a Golang based open source static site generator. That said I didn’t do a whole lot to set it up:

* Exported by Medium content. It was HTML. So I converted it to Markdown which only sort of worked.
* Cut my draft posts.
* Setup [NetlifyCMS](https://www.netlifycms.org) so I could more easily upload posts from my iPad and enforce consistent formatting.
* Tried out a handful of themes, none of which I loved, and eventually got stuff working.
* Did some crazy stuff to add an RSS generator to the theme I picked, [Hugo-PaperMod](https://github.com/adityatelange/hugo-PaperMod/), since it didn’t have built in support (That’ll come up later).
  That was about it.

## June 2021 Update

Given I can start writing again I decided to sit down and clean everything up. My setup was pretty alright, but I thought it could be better. I honestly started and ended with the same components, by and large they were great:

|                   |                                                                            |
| ----------------- | -------------------------------------------------------------------------- |
| Hosting Platform  | [Netlify](https://www.netlify.com)                                         |
| Framework         | [Hugo](https://gohugo.io)                                                  |
| Theme             | [Hugo-PaperMod](https://github.com/adityatelange/hugo-PaperMod/)           |
| Writing Interface | [Ulysses](https://ulysses.app)                                             |
| Data Interface    | [NetlifyCMS](https://www.netlifycms.org)                                   |
| Data Storage      | [GitHub](https://github.com)                                               |
| Analytics         | [Netlify Analytics](https://docs.netlify.com/monitor-sites/analytics/#app) |

### Netlify

[Netlify](https://www.netlify.com) is a comprehensive static site hosting system. Basically GitHub Pages Plus, Netlify added a lot of what I was missing, including a [CMS](https://www.netlifycms.org) (basically a [WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG) Markdown editor) that backs into GitHub (which enables deployment and branch based [Deploy Previews](https://docs.netlify.com/site-deploys/deploy-previews/)) and basic analytics (I presume just showing the web server logs they were already collecting, so no add-ons).  All this for $9 a month (my only recurring cost). Couldn’t ask for much more.

### Hugo

The skeleton is built using the Golang based static site generator [Hugo](https://gohugo.io). I had used Jekyll before, but when rebuilding I figured given I write more Go than Ruby I should use a Go based static site generator (I thought about [Pelican](https://blog.getpelican.com), but compiled seems like it’d be faster). Hugo is super fast, has a lot of great templates, and is easy to modify where necessary.

### Ulysses

While NetlifyCMS is great for workflow it isn’t the nicest writing experience. For this, long term, I use Ulysses.

![Ulysses for MacOS](/images/uploads/ulysses_blogging.png "Ulysses for MacOS")

> A pleasant, focused writing experience combined with effective document management, fast syncing and flexible export options make Ulysses the first choice for writers of all kinds.

Ulysses simplifies writing by syncing everything between all my devices, providing a minimal and clean interface, as well as making it possible to organize research. My biggest beef with Ulysses is no support for Markdown tables, but otherwise I can just write in Ulysses and then go into NetlifyCMS to publish.

### Cleanup

So up to this point I hadn’t changed anything (good choices mostly worked out). I kept everything in Hugo hosted on Netlify backed by GitHub the way it had been after moving off of Medium, but things had gotten a bit crufty the way on old system does. I’d built a bunch of custom changes to the theme, things were missing, but since my initial deploy Hugo-PaperMod a lot had been added.

So I started over. Full on scorched earth. 🔥🌎 I removed everything from my repo except for the Markdown files and the readme. Regenerated the Hugo site from the start and added my them back in. Re-added the static pages for NetlifyCMS and everything was back to normal.

![New Blog Layout](/images/uploads/sroberts_io_202106_screenshot.png "New Blog Layout")

At that point all I had to do was configure a few new things and fix a bunch of errors introduced by the Medium export. The site now has search, better favicon/top icon support, cleaner RSS, added social networks (like Keybase).
Now I just have to get to writing.
