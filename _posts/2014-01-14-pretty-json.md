---
layout: post
title: Pretty JSON is Pretty (Useful)
---

So as initially suggested I haven't been good about blogging yet. I've been quite busy with work. But I did want to pass along one small tip I've picked up.

A lot of the work I've been doing has been a combination of Ruby/Python and [command line](https://github.com/eyenx/omzsh) data parsing. In much of this shell I'm working through [JSON documents](http://www.json.org) on the command line, often using commands like:

> cat foo.txt \| grep \"foo\" \| sort \| uniq

I've learned a lot about composing commands and the [beauty of the Unix philosophy](http://www.faqs.org/docs/artu/ch01s06.html), it's been great. But I hit a lot of issues with some tools that initially spit out "ugly", overly terse JSON:

```json
[{"foo": "foo", "bar": [1, 2, 3], "baz": "baz"}]
```

[Valid](http://jsonlint.com)? Yes, but difficult to work with, especially on the command line with the simple ```grep``` commands I was using. I got close to writing a tool to use [Python](http://www.python.org) or [Ruby](https://www.ruby-lang.org/en/)'s built in conversion [until I found](http://stackoverflow.com/questions/352098/how-can-i-pretty-print-json):

> cat foo\_ugly.json \| python -tmjson.tool > foo\_pretty.json

Which spit out the far easier to read and work with:

```json
[
  {
    "foo": "foo",
    "bar": [1, 2, 3],
    "baz": "baz"
  }
]
```

Just a little tip if you're also using lots of JSON on the command line.

---

So a number of people were kind enough to respond on Twitter to my post on this and recommend I look into [./jq](http://stedolan.github.io/jq/), which describes itself as _"jq is like ```sed``` for JSON data_. I've played with it a bit and must say it seems like a very cool tool that could certainly help with what I'm doing. I'm going to use it for a few days, dig into it more, and maybe post a follow up.

Thanks @[danthompson](http://whoisdanthompson.com), @[pengynn](http://me.wynn.fm), & @[1stvamp](http://1stvamp.org)!
