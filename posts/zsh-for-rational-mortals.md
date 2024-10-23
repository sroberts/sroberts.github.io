---
title: zsh for Rational Mortals
date: 2019-06-05T20:00:56.794Z
draft: false
tags:
  - terminal
lastmod: 2024-05-13T17:06:55.842Z
---

{{< tweet user="sroberts" id=1135911381536870400 >}}

This post, my first in quite awhile, is inspired by my good friend [Phil](https://twitter.com/sroberts/status/1135911381536870400). I understand these sorts of changes, and why they give people pause, but I see this as a big step forward.

## zsh

If you haven't heard of it [Z Shell](https://zsh.sourceforge.io) (also known as `zsh`) it is a modern shell that works in place of a shell like bash (either as a default or in my case post install choice). A shell is a funny thing though: 95% of computer users don't know about shells at all, 3% know about it but don't give it much thought (just run what you're told), and for the last 2% it's one of the most important parts of a system.

Okay... if you're still reading I assume you're that last two percent. For that two percent there are two main theories:

- **Don't Touch Anything:** Leave all the defaults as they are. That way any system you land on will be setup as you expect.
- **Customize Everything:** Make it yours, tweak whatever you want to tweak, make every aspect of the system _exactly what you want_.

Now there's pros and cons to both. In orgs that do a lot of pairing a highly customized terminal will slow down one of the two members of the pairing team. I work a lot in terminal, generally on my own, so anything I can add to speed up my process, make things easier or more familiar, is worthwhile.

There are big, comprehensive packages for tweaking Z Shell like [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) which includes elaborate features but for me I like to take a simpler, slower, more progressive approach. Here's my `zshrc` file, the configuration for shell:

{{< gist sroberts 6eca99edf558c7e40543968007ebebe4 >}}

I try to keep even my own code, especially code I don't touch often, well documented. Even my `zshrc`. Here's what's going on:

- Colors and stuff for my shell, for readability.
- Make sure my terminal uses UTF-8 for all the modern goodness.
- Set Homebrew to update regularly so I don't have tons of out of date software laying around.
- Aliases are pretty simple in Z Shell, which is really nice to have (and come to think of it I should do more with). Mine are all to make sure I'm using [Python 3 not system Python 2.7](https://pythonclock.org) because that's the correct Python.
- Adding to your path (where the system looks for executables or other things) is pretty common. I used to write a lot of [Golang](https://golang.org) so my `zshrc` makes sure that will work as expected.
- The `SPACESHIP_VI_MODE_SHOW` is a specific tweak on the terminal theme I use, which is installed by zplug.

Speaking of...

## [zplug](https://github.com/zplug/zplug)

Probably the biggest part of my `zshrc` that makes significant changes are the zplug modules. zplug is a package manger for Z Shell, similar to `apt` on Ubuntu or Homebrew on MacOS. It lets you easily add complex Z script based modules to your configuration and have them loaded and added at run time. Modules can do basic things, like add specific aliases, all the way up to complicated things like themes.

I currently run the following:

| Plugin                                                                                          | Description                                                                              |
| ----------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| [lukechilds/zsh-better-npm-completion](https://github.com/lukechilds/zsh-better-npm-completion) | I was writing a lot of JS for awhile, which means lots of NPM.                           |
| [mafredri/zsh-async](https://github.com/mafredri/zsh-async)                                     | Honestly I'm not 100% sure why I have this.                                              |
| [denysdovhan/spaceship-prompt](https://github.com/denysdovhan/spaceship-prompt)                 | My theme plugin, Spaceship is low key, clean, but has some nice Powerline based add ons. |
| [zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)               | Because I don't remember every shell command ever.                                       |
| [zsh-users/zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)       | More shell pretty, making text more readable with better highlighting.                   |

It's not much, but it's most of what I need. As I see a module I want I add it, when I realize I'm not using or don't like something I remove it (like I'm probably going to go do with the `zsh-better-npm-completion` and `zsh-async` after this post).

Once it's setup you just run `zplug install` to install the plugins in `zshrc` and you're good to go.

## Why Bother?

Setting all this up is honestly a lot of effort, so why bother? Zshell and my `zshrc` files are just a part of my greater [Dotfiles](https://dotfiles.github.io), which I maintain (though not publicly because I'm paranoid) to help me automate system setup and management. There are a few big reasons:

- **Repeatability:** Most obvious is the ability to set multiple systems up and end up with the same workspace. I'll share a story about that.
- **Deterministic System State:** Good system configuration files mean if something gets out of whack it's easy to return to a known good state. A quick `git reset --hard` and a rerun of your setup script means everything is back to normal.
- **Using Development Flows:** As stated above I love that my system configuration and setup is in code, and can be managed with code flows. I can try things in PRs, see what works, blow it away, and go back to known good. I can use continuous integration to make sure stuff works.
- **Learning from Others:** Lastly I can use the code others develop, learn from it, tweak it, change it, be inspired by it.

Having well manicured, tested, and reliable dotfiles can save your bacon. I was once doing a bit of pro-bono IR work and took a new, clean Windows system (where I didn't have any setup automation). Turns out I was even more out of date on Windows than I thought I was and hardly got anything done the first day (not good in an emergency IR). I ended up going out, getting a new system, running my dotfiles, and was up and at work before finishing my second cup of coffee for the day. I would have wasted days setting up that system for all the things I needed, but my dotfiles were ready to help, including my `zsh` config.

Getting started with Z Shell is a great place to begin building out your own dotfiles, feel free to start with my `zshrc` and make it your own!
