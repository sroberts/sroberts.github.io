---
layout: post
title: Pretty JSON is Pretty (Useful)
---

So as initially suggested I haven't been good about blogging yet. I've been quite busy with work. But I did want to pass along one small tip I've picked up.

A lot of the work I've been doing has been a combination of Ruby/Python and [command line](https://github.com/eyenx/omzsh) data parsing. In much of this shell I'm working through JSON documents on the command line, often using commands like:

> cat foo.txt | grep \"foo\" | sort | uniq

I've learned a lot about composing commands and the beauty of the Unix philosophy, it's been great. But I hit a lot of issues with some tools that intially spit out "ugly", overly terse JSON:

```json
[{"foo": "foo", "bar": [1, 2, 3], "baz": "baz"}]
```

Valid? Yes, but difficult to work with, especially on the command line with the simple ```grep``` commands I was using. I got close to writing a tool to use Python or Ruby's built in conversion [until I found](http://stackoverflow.com/questions/352098/how-can-i-pretty-print-json):

> cat foo_ugly.json | python -tmjson.tool > foo_pretty.json

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