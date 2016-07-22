---
layout: post
title: Command-line Spell Checking with Aspell
description: 'Wun dae eye wll spll gud.'
---

In an effort to improve my "Unix" skills I'm trying to do more and more on the command line, such as writing this blog. This has worked out for me in a lot of ways, making much of my work faster, less environment dependent, and easier to reproduce/script. I've learned lots of tricks to help with this, but recently came across one of the best ones: Aspell.

First a confession: people get into the computer industry for lots of reasons. My reasons were kind of different: I couldn't spell and have terrible handwriting. In 4th grade being told this magic box would make my ideas legible and spelled correctly was game changing for me. But I digress.

So while Vim is great and all one of the things I struggled with is being able to spell check documents. Then I found Aspell:

> GNU Aspell is a Free and Open Source spell checker designed to eventually replace Ispell. It can either be used as a library or as an independent spell checker. Its main feature is that it does a superior job of suggesting possible replacements for a misspelled word than just about any other spell checker out there for the English language. Unlike Ispell, Aspell can also easily check documents in UTF-8 without having to use a special dictionary.

I've been really impressed with Aspell and after using it a few days it's gotten a place on my "must have software" list. It's pretty simple:

```
$ aspell -c _posts/2014-01-20-commandline-spellchecking-with-aspell
```

Brings up a straight forward text interface:

<img src="/public/aspell.png" alt="aspell" style="width: 700px;"/>

The suggestions are usually spot on and it has most of the features you'd expect from a mature spell checker in an application like [Microsoft Word](http://office.microsoft.com/en-us/word/) or [Apple Pages](http://www.apple.com/mac/pages/), both of which I rarely touch anymore given the strong the combination of Vim, Aspell, and Markdown. If you're working on lots of text documents on the command-line I cannot recommend it enough.

**Bonus:** If you're just getting into Vim, as I am, I cannot recommend [Vim-Adventures](http://vim-adventures.com) (billed as "Learning VIM while playing a game") and Square's [Maximum Awesome](https://github.com/square/maximum-awesome) (billed as "Config files for vim and tmux, lovingly tended by a small subculture of peace-loving hippies. Built for Mac OS X.") enough. They've made getting into Vim straight forward and fun.
