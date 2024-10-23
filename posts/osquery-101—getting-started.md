---
title: osquery 101 — Getting Started
date: 2016-01-26T05:00:00.000Z
tags:
  - network-defense
  - macOS
---

I admit it… I’m a fanboy. A straight up [osquery](http://osquery.io/) fanboy.

Oh… what is osquery you ask? Good question there sport.

> _osquery allows you to easily ask questions about your Linux and OSX infrastructure. Whether your goal is intrusion detection, infrastructure reliability, or compliance, osquery gives you the ability to empower and inform a broad set of organizations within your company._

That’s how Facebook describes it. I’d say **osquery is the most effective way available to monitor an OSX or Linux host for security**. But that’s just me. Still not bad no matter which definition you prefer.

The big question everyone asks though is how do you get started with osquery and so without further ado:

### Install osquery

This one is pretty simple. Just follow these [handy instructions](https://osquery.io/downloads/).

**OSX Side Note:** _If you’re on OSX and a fan of Homebrew (as I am) you’ll want to skip Homebrew this time and install the package directly. Homebrew gets weird about running things as root later on, and that will be a pain. Safe yourself the pain._

### Using osqueryi

osquery provides two main interfaces to the user: osqueryi and osqueryd (we’ll get to osqueryd in another post). osqueryi is a [REPL (Read-Evaluate-Print Loop)](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) similar to `$ irb` or `$ python`. This lets you input a command and get back an immediate response. We can use this for a few things:

- One off, spot checking of specific system attributes.
- Developing new queries.
- Learning your way around osquery.

So lets give it a try. Get started by typing `osqueryi` at your terminal.

![](https://cdn-images-1.medium.com/max/800/0*5FAx1IMxPPmDuI8h.png)

Now that you’re at the prompt you’re ready to start looking for things. osquery uses the [sqlite query language](https://www.sqlite.org/lang.html) for simplicity and descriptiveness. The most basic query format is:

```
SELECT columns FROM table;
```

_Don’t forget the semicolon “;” at the end of your query! You wouldn’t like it without the semicolon. In that it won’t do anything._

For example lets take a look at the [OSX kernel extensions](https://developer.apple.com/library/mac/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) I have installed:

![](https://cdn-images-1.medium.com/max/800/0*no-xXSEcEOOeycGv.png)

Ok, so that found the data I wanted, but a bit too much. Every OSX system has Apple written kernel extensions, which makes those less interesting. Using the sql concept of a _where_ clause we can limit this just to non-Apple kernel extensions:

![](https://cdn-images-1.medium.com/max/800/0*IsEjr1UMlH-j1avx.png)

Much more useful. Lets take it one step further and make it more readable with sorting:

![](https://cdn-images-1.medium.com/max/800/0*cWSeYSKsnHrBa1fk.png)

For those playing at home you can see I have 11 kernel extensions for 5 applications (and OSX itself). The final query that got this information is:

```
SELECT name FROM kernel_extensions WHERE name NOT LIKE 'com.apple%' ORDER BY name;
```

Pretty straight forward, but by now the power should be evident. As you practice more you can express powerful and complex ideas using this syntax. For more on syntax take a look at [the SELECT documentation for sqlite](https://www.sqlite.org/lang_select.html). This coupled with the [osquery Tables reference](https://osquery.io/docs/tables/) will give you most of what you need. A couple of key, non-query, commands will help you get started:

| Command   | Function                                         |
| --------- | ------------------------------------------------ |
| `.help`   | Gives you the osqueryi help dialogue.            |
| `.schema` | [TABLE] Prints the table columns and data types. |
| `.exit`   | It isn’t exit or quit or exit().                 |

If you want some examples of what you can look for and how you can use the sqlite syntax take a look at the [osquery Packs](https://osquery.io/docs/packs/). Here are a few of my favorites:

### Incident Response: open_sockets

```sql
select distinct pid, family, protocol, local_address, local_port, remote_address, remote_port, path from process_open_sockets where path <> '' or remote_address <> '';
```

A typical SELECT FROM WHERE style query to find open network connections. Combine this with an IP blacklist to identify C2 activity.

### Incident Response: startup_items

```sql
select * from startup_items;
```

Startup Items is a common way for OSX malware to persist between restarts. Most users don’t even notice it’s there.

### Vulnerability Management: chrome_extensions

```sql
select chrome_extensions.* from users join chrome_extensions using (uid);
```

Chrome extensions have a scary amount of access, especially in web based workflows. They’re worth investigating.

## Want to Learn More?

I do too. There’s a lot to osquery. It’s not a solution, it’s a framework. On one hand that makes it customizable, on the other that means many parts of using it are _left to the user_. It may be free, but that means it’s an investment of time rather than money.

[Kevin Thompson](https://twitter.com/bfist) and I spoke about osqueryi and more at BSidesDFW 2015 in our presentation [Responding @ Scale - osquery for Mass Incident Detection & Response](https://speakerdeck.com/sroberts/responding-at-scale-osquery-for-mass-incident-response-and-detection)

I’ll explore some of these ideas from our presentation in the next post in this series: **osquery 110 — Programmatic osqueryi**.
