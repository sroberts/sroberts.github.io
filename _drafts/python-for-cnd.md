---
layout: post
title: Python for CND
---

One thing I constantly harp on while talking to people beginning in the security community is the importance of learning to code. In my mind is a crime that we have so many "security professionals" who can barely write a lick of code.

## What is Python

From [Python.org/about:](https://www.python.org/about/)

> Python is powerful... and fast;
plays well with others;
runs everywhere;
is friendly & easy to learn;
is Open.Python is powerful... and fast;
plays well with others;
runs everywhere;
is friendly & easy to learn;
is Open.

Python is an interpreted language, meaning the `python` application takes the same `.py` file you write code in and runs that for you, without a compilation step in between (if you want a compiled language [I recommend looking at Golang](https://sroberts.github.io/2016/07/18/go-for-dfir/)). Python runs about anywhere and if you have a MacOS or Linux computer you probably already have Python installed.

## Why Use Python for Security?

Because all the cool kids are doing it? Python is the default programming language for most network security types, having largely taken the mantle from Perl. It's easy to write, whether its a [basic script for rearranging data](https://github.com/sroberts/code-phrase-generator) or [elaborate large scale distributed security tools](https://github.com/google/grr), has lots of great libraries for common security tasks (we'll look at some of them later), and quick to learn.

## Resources for Learning Python

Learning any language is never just about learning to write code, though that's the first place to start. Learning a language means learning it's syntax, but also conventions, libraries & tooling, as well as how to test. It also often helps to look at projects others have done to get the lay of the land. Here's some resources to get started:

### Core Language Syntax

Start with [CodeAcademy: Python](https://www.codecademy.com/learn/python) to learn the basic syntax. It's free, there's no setup, and you'll learn enough to be dangerous in an afternoon. Ready to go deeper? You want [Learn Python the Hard Way](https://learnpythonthehardway.org/) for a pretty deep dive into Python, using your own machine. If you need a few littler reminders check out the [Learn X in Y minutes: Python3](https://learnxinyminutes.com/docs/python3/) cheatsheet.

> __Aside: Python 2.7 vs Python 3__ If you want to get Python folks at each other just bring up Python3. Released a few years


- Libraries
    - Flask/Django
    - Requests
    - UtilityBelt
- Testing & Continous Integration
- Packaging
- Architecure


### Books

- [Gray Hat Python](https://www.nostarch.com/ghpython.htm) - Especially strong on Python for Reverse Engineering.
- [Black Hat Python](https://www.nostarch.com/blackhatpython) - A slightly more offensively focused take.
- [Violent Python: A Cookbook for Hackers, Forensic Analysts, Penetration Testers and Security Engineers](http://www.goodreads.com/book/show/16192263-violent-python) - Honestly I haven't read it, but it's a Python security book so it fits the list.


### Key Libraries

### Awesome Projects

- OSXCollector


## Companies Using Python for Security

Basically everyone. Honestly it seems counterproductive to list them. Aside from Metasploit Python is the go to scripting language for most IR firms and the language of choice for the open source security world.

## In Conclusion

While not everyone in security will write code as a job almost everyone can benefit from writing some code to assist in their job. Even basic data manipulation is a key skill that becomes more useful the more you do it. Given Python's wide use, great libraries, and ease to learn it's an ideal place to get started. While there are other languages that do specific things better almost none can claim to do everything as well as Python.
