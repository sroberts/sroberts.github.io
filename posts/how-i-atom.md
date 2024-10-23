---
title: "How I\_Atom"
date: 2015-06-06T04:00:00.000Z
tags:
  - development
---

> Update - April 2019: To be honest I don't Atom anymore. I switched to [Visual Studio Code](https://code.visualstudio.com) in the middle of 2017 while writing TypeScript and Golang and haven't looked back.

During the time I’ve been at [GitHub](https://www.github.com/) one of the coolest projects to come out has been [Atom](https://atom.io/), GitHub’s own text editor. I’ve been using it since the day it got released internally at GitHub and I can say Atom is one of my 3 top used applications and an essential part of my work flow.

What makes Atom shine, even next to a great editor like [Sublime Text](http://www.sublimetext.com/) (My old favorite) or a classic like [VIM](http://www.vim.org/), is it’s extensibility. Getting started with such highly extensible tool is tough, so here’s a couple of ideas based on how I use Atom that might get you started.

![](https://cdn-images-1.medium.com/max/800/0*uu1RCcAauvSeYigF.png)

### How I Use Atom

| %   | Language                                                      | Use                                                                                                                                                                                                                                                                                                                                                                          |
| --- | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 45% | [Markdown](https://help.github.com/articles/markdown-basics/) | Markdown is the standard document format for most things at GitHub and given how comfortable Markdown is I’ve shifted most of my personal documents and writing (including this blog) to Markdown.                                                                                                                                                                           |
| 35% | [Python](https://www.python.org/)                             | GitHub is a [Ruby](https://www.ruby-lang.org/en/) shop it’s true, but Python is the language of security (yes yes, I know about [Metasploit](https://github.com/rapid7/metasploit-framework)). I typically write smaller Python utilities, but occasionally dig into bigger [Django](https://www.djangoproject.com/) projects like [GRR](https://github.com/google/grr).     |
| 10% | [CoffeeScript](http://coffeescript.org/)                      | Not a terribly common language for a security engineer CoffeeScript is the language of [Hubot](https://hubot.github.com/). DevOps-ing security tools is so awesome [I’ve already talked about it](http://sroberts.github.io/2014/05/14/using-robots-to-fight-bad-guys/)… [multiple times](https://speakerdeck.com/sroberts/building-your-own-dfir-sidekick-threads-edition). |
| 5%  | HTML/CSS/JS                                                   | Mostly for this blog. 5% Randomness A little [Go](http://golang.org/) these days. Some system automation like Shell and [Ansible](http://www.ansible.com/home).                                                                                                                                                                                                              |

### [Packages](https://atom.io/packages)

The easy place to start with Atom is packages. Here are my favorites:

#### [Zen](https://atom.io/packages/zen)

You can pay a fair bit of money to buy a _minimalist_ text editor. Or you can just use Zen. This package (by GitHub’s CEO [@defunkt](https://github.com/defunkt) no less) turns Atom into a 100% focused text only editor experience.

![](https://cdn-images-1.medium.com/max/800/0*cEYC4acsiVaztj3U.png)

#### [atom-beautify](https://atom.io/packages/atom-beautify)

This package takes structured file types and normalizes them, presenting them in a cleaner, more humanly grep-able way. I most commonly use it to take JSON from APIs, which is often presented as one line, and adding the new lines and indenting that makes it human readable.

#### [dash](https://atom.io/packages/dash)

I think of Atom as more than a text editor and less than an IDE, in the best ways possible. Two big IDE features that I’ve added to my Atom setup and the first one is getting documentation from [Dash](https://kapeli.com/dash) using the dash & dash-on-cursor Atom packages. Just hitting Ctrl+h instantly does a context specific search for the term you’re on and pulls it up in Dash. Whats even better is this is offline documentation, so even in low/no bandwidth situations you can keep working.

![](https://cdn-images-1.medium.com/max/800/0*Tg0dVMqI7B_0m55w.png)

You don’t have [Dash](https://kapeli.com/dash)? If you’re a developer using a Mac then you’re doing it wrong, I can’t recommend it enough.

Date lets you print a variety of date and timestamps. Highly useful if you’re writing up documentation on something like an incident. Which I do…. a lot.

#### [file-icons](https://atom.io/packages/file-icons)

This package gives a prettier, more expressive icon set for the sidebar and tabs of Atom. These visual identifiers are often handy given modern projects base on web frameworks have so many different types of files involved.

#### [go-plus](https://atom.io/packages/go-plus)

If you’re using [Go](http://golang.org/) you’ll take a look at this package, marvel in the awesome, and instantly install it. If you aren’t it’s basically useless, and pops a lot of annoying errors.

#### [linter](https://atom.io/packages/linter), [linter-write-good](https://atom.io/packages/linter-write-good), [linter-pylint](https://atom.io/packages/linter-pylint), & [jsonlint](https://atom.io/packages/jsonlint)

The other major IDE like function I get out of Atom is linters for realtime syntax checking. [Linters](http://en.wikipedia.org/wiki/Lint_%28software%29), which let you know when you’re not complying with the language specification, are a great example of one of the IDE like benefits you can have in Atom. Think of it like spell check for programming languages, linters let you know when you’re writing code incorrectly.

The linter package is the start, then you can hunt down the linters most relevant to your own development.

#### [merge-conflicts](https://atom.io/packages/merge-conflicts)

Ahhh the bane of every Git users existence, the [merge conflict](https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/). The merge-conflicts package helps make these easier to deal with, giving you visual queues and instantly snapping to each conflict.

I don’t hit conflicts that often, but when I do this plug makes it easy to sort through them.

#### [regex-railroad-diagram](https://atom.io/packages/regex-railroad-diagram)

![](https://cdn-images-1.medium.com/max/800/0*R48osRBFXmfCRL_A.)

Regular Expressions are highly useful but complicated things and it’s often easy for one character to change the meaning or function of a regex entirely. The regex-railroad-diagram gives you a visual aid for understanding any regex. I rely on it heavily.

#### [sort-lines](https://atom.io/packages/sort-lines)

Super simple, but super useful. While you wouldn’t want to sort code this comes in useful when working with lists.

### [Themes](https://atom.io/themes)

I won’t go too nuts talking about themes. It’s 100% personal preference. Atom Themes come in two pieces, UI & syntax. I find the best option is to play with them. Some favorites are:

- [Outlander Syntax](https://atom.io/themes/outlander-syntax) \+ [Outlander UI](https://atom.io/themes/outlander-ui)
- [Seti Syntx](https://atom.io/themes/seti-syntax) \+ [Seti UI](https://atom.io/themes/seti-ui)
- [Unity UI](https://atom.io/themes/unity-ui)

Personally I swap mine in and out every couple weeks. Right now I’m using the built in Atom Light option for both.

### Other Recommended Packages:

- [vim-mode](https://atom.io/packages/vim-mode): Coming from everyone’s favorite terminal editor and miss your key commands, you can hold on to them!
- [minimap](https://atom.io/packages/minimap): Hold over from Sublime Text? minimap will make you feel at home.

### Tricks

- Meta-Shift-p: Everything. Much of Atom’s power hides behind the text menu. You’ll miss it otherwise.
- Take a look at each package & theme for their own settings. These tweaks can often make a big difference. For instance I always check the “Force Show” option on the file-icons package.
- Browsing the Packages & Themes sections of the Atom sites will probably have piles of other useful packages based on your specific needs.

### How I Don’t Use Atom

**Logs.** It’s that simple. Atom doesn’t handle files 2mb or bigger, so it’s a _no go_ for log analysis except for the smallest examples. During my switch to Atom log analysis was the main situation I’d go back to Sublime Text, but at this point I do almost everything on the commandline. Sed/Awk/Grep and ./jq are amazing tools and at this point I think I’m faster working through logs on the commandline than I ever was in a text editor.
