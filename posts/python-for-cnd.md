---
title: Python for CND
date: 2016-11-30T06:00:00.000Z
tags:
  - development
  - network-defense
---

One thing I constantly harp on while talking to people beginning in the security community is the importance of learning to code. I think it is awful that we have so many _security professionals_ cannot write a line of code. It’s useful for automating common tasks, gathering & manipulating data, almost anything you can imagine. I think everyone should learn some coding and Python is the best place to start.

### What is Python

From [Python.org/about:](https://www.python.org/about/)

> _Python is powerful… and fast; plays well with others; runs everywhere; is friendly & easy to learn; is Open.Python is powerful… and fast; plays well with others; runs everywhere; is friendly & easy to learn; is Open._

Python is an interpreted language, meaning the `python` application takes the same `.py` file you write code in and runs that for you, without a compilation step in between (if you want a compiled language [I recommend looking at Golang](https://sroberts.github.io/2016/07/18/go-for-dfir/)). Python runs about anywhere and if you have a MacOS or Linux computer you probably already have Python installed.

Python is beautifully simple. Here is Hello World:

{{< gist sroberts 64aaba445c1ad475e42b3c0162866bd7 >}}

<!-- TODO: FIX THIS It rarely gets much simpler than that. Lets demonstrate something a bit more complicated:

Here we’re using a library called [Requests](http://docs.python-requests.org/en/master/) to grab the [SANS Infocon status](https://isc.sans.edu/infocon.html) from their web service. Then we check to make sure the response had an [HTTP status code 200](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#2xx_Success) and return the value to print, otherwise if we can’t get the Infocon successfully we’ll return an error. _Contrived?_ Yes. _Simple?_ Of course. _Useful as a jumping off point?_ Absolutely. -->

### Why Use Python for Security?

Because all the cool kids are doing it? Python is the default programming language for most network security types, having largely taken the mantle from Perl. It’s easy to write, whether its a [basic script for rearranging data](https://github.com/sroberts/code-phrase-generator) or [elaborate large scale distributed security tools](https://github.com/google/grr), has lots of great libraries for common security tasks (we’ll look at some of them later), and quick to learn.

### Resources for Learning Python

Learning any language is never just about learning to write code, though that’s the first place to start. Learning a language means learning it’s syntax, but also conventions, libraries & tooling, as well as how to test. It also often helps to look at projects others have done to get the lay of the land. Here’s some resources to get started:

### Core Language Syntax

Start with [CodeAcademy: Python](https://www.codecademy.com/learn/python) to learn the basic syntax. It’s free, there’s no setup, and you’ll learn enough to be dangerous in an afternoon. Ready to go deeper? You want [Learn Python the Hard Way](https://learnpythonthehardway.org/) for a deep dive into Python, using your own machine. If you need a few syntax reminders check out the [Learn X in Y minutes: Python3](https://learnxinyminutes.com/docs/python3/) cheatsheet.

> **_Aside: Python 2.7 vs Python 3_** If you want to get Python folks at each other just bring up Python3. Released a few years Python3 was meant to be a significant upgrade, fixing lots of old structural issues that couldn’t be fixed earlier because they would break old code. Many people have been resistant, and even though it’s been out for years Python3 still isn’t the default. I focus on writing Python3, but your mileage may vary and your organization may do things very differently.\_

One of the nicest things about learning an interpreted language like Python (or Ruby, Perl, etc) is being able to learn using a Read Evaluate Print Loop (Usually referred to as a REPL). You can start a REPL for Python by just typing `python` at a command prompt without any arguments. This lets you write Python line by line, getting the output immediately. It’s a great way to do things quickly or just experiment.

### Python Security Books

Python is so common in security that there are a number of great security centric Python books. These are great ways to learn Python in a security specific context.

- [Gray Hat Python](https://www.nostarch.com/ghpython.htm) — Especially strong on Python for Reverse Engineering.
- [Black Hat Python](https://www.nostarch.com/blackhatpython) — A slightly more offensively focused take.
- [Violent Python: A Cookbook for Hackers, Forensic Analysts, Penetration Testers and Security Engineers](http://www.goodreads.com/book/show/16192263-violent-python) — Honestly I haven’t read it, but it’s a Python security book so it fits the list.

### Packages

One of the best things about Python is the multitude of libraries that already exist before you write your first line of code. These range from basic data manipulation libraries all the way up to complex web frameworks and data mining toolsets.

In Python all packages are managed using `pip` (yeah yeah easy_install & eggs and a bunch of other ways, but lets keep it basic). Searching for a new tool is as easy as `pip search virustotal`, which will return all the Python packages related to everyone’s favorite malware service. Decide you want to use one? A quick `pip install virustotal-api` and you’re off to the races (Once you get a bit further down the road you’ll want to learn about using [virutalenv](http://docs.python-guide.org/en/latest/dev/virtualenvs/) as well).

What libraries you want to use depends a lot on the work you’re doing, but here are a few core ones most security minded Python developers will want to use:

- **[Flask](http://flask.pocoo.org/)** The go to for small webapps, Flask is especially useful for REST API based tools.
- **[Requests](http://docs.python-requests.org/en/master/)** Requests is the only Non-GMO HTTP library for Python, safe for human consumption.
- **[yolothreat/utilitybelt](https://github.com/yolothreat/utilitybelt)** A Python library for being a CND Batman….

There are literally thousands more, but these are three I reach to often.

### Awesome Python Projects

There are plenty of examples of great security tools using Python, many of which I’ve already talked about. Here’s a new set I’d recommend looking into:

| Library                                                                    | Description                                                                            |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| [viper-framework/viper](https://github.com/viper-framework/viper)          |  Binary analysis and management framework                                              |
| [MITRECND/chopshop](https://github.com/MITRECND/chopshop)                  |  Protocol Analysis/Decoder Framework                                                   |
| [threatstream/symhash](https://github.com/threatstream/symhash)            |  A tool to create symbol table hashes for Mach-O executables                           |
| [mwielgoszewski/doorman](https://github.com/mwielgoszewski/doorman)        |  an osquery fleet manager                                                              |
| [Neo23x0/Loki](https://github.com/Neo23x0/Loki)                            |  Simple IOC and Incident Response Scanner                                              |
| [mpars0ns/scansio-sonar-es](https://github.com/mpars0ns/scansio-sonar-es)  |  Python scripts to parse scans.io ssl data and ingest into elasticsearch for searching |
| [PUNCH-Cyber/stoq](https://github.com/PUNCH-Cyber/stoq)                    |  An open source framework for enterprise level automated analysis.                     |

These are all under active development and great tools to consider sending pull requests to.

### Ready For More?

Programming is often far more than syntax and libraries. Here are some things you’ll want to start investigating next:

- VirtualEnv & Pip: [The Hitchhiker’s Guide to Python: Virtual Environments](http://docs.python-guide.org/en/latest/dev/virtualenvs/)
- Testing: [The Hitchhiker’s Guide to Python: Testing Your Code](http://docs.python-guide.org/en/latest/writing/tests/)
- Setup your Editor for Python: [Atom](http://www.jonobacon.org/2015/11/16/atom-my-new-favorite-code-editor/) & [vim](https://www.fullstackpython.com/vim.html)

### Companies Using Python for Security

Basically everyone. Honestly it seems counterproductive to list them. Aside from Metasploit Python is the go to scripting language for most IR firms and the language of choice for the open source security world.

### In Conclusion

While not everyone in security will write code as a job almost everyone can benefit from writing some code to assist in their job. Even basic data manipulation is a key skill that becomes more useful the more you do it. Given Python’s wide use, great libraries, and ease to learn it’s an ideal place to get started. While there are other languages that do specific things better almost none can claim to do everything as well as Python.
