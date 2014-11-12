---
layout: post
title: Learning Git & GitHub
---

I suppose it makes sense that when you work for a company everyone assumes you know everything about using its products. When I worked at [Symantecs Managed Security Services](http://www.symantec.com/managed-security-services) people asked me all the time how to use the antivirus. It's a normal assumption, even if it's off base.

So working at [GitHub](http://www.github.com) I get asked [git](http://git-scm.com/) & GitHub questions all the time. #REALTALK: The fact is I'm not a great git user. I don't rebase. I'm terrible about using bisect. There are all kinds of features I know exist but hardly ever use. That said I know about 90% of what I need to use git effectively, and I've gotten pretty good at GitHub (the product) itself. So here's where I learned and what I think will help you get the most out of git and GitHub.

## Learning Git
Just in case you don't know what Git is:
>Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
>
>Git is easy to learn and has a tiny footprint with lightning fast performance. It outclasses SCM tools like Subversion, CVS, Perforce, and ClearCase with features like cheap local branching, convenient staging areas, and multiple workflows.

To learn git I recommend starting out with [Try Git](http://try.github.io/levels/1/challenges/1). This is a quick, 15 min tutorial that introduces the core concepts of git that you'll need and is enough to get started. It's pretty much the ideal place to start, and you don't even need to install anything.

Try Git is certainly enough to get yourself started, but eventually you'll want to move on to some of the more advanced command line options. To learn those I recommend [Git Immersion](http://gitimmersion.com/). Git Immersion is actually done on your own system's command line and teaches things like rebasing vs merging, tagging, and even resolving conflicts.

## Learning GitHub
Between those resources you'll have a pretty solid base in using Git. Those concepts will get you most of the way towards using GitHub effectively, but GitHub does add a few concepts on top of Git such as Comments, Issues & Pull Requests, and Releases.

At it's core the most important part is what we call "The GitHub Flow":tm::

0. The master branch is always deployable. Always.
1. Create a branch from master of a repository you want to contribute to.
2. Make commits to the code in the branch.
3. Push the branch back up to GitHub, you'll get an interface to create a Pull Request.
4. You (and the other contributors to the repo) can now commit more code, discuss changes using comments, and finalize the code.
5. At this point a repo owner can merge the changes.

There's an even better [graphical introduction of the GitHub Flow here.](https://guides.github.com/introduction/flow/) If you can master those 5 steps you'll be a GitHub master.

## Being Even more Awesome at GitHub

Now that you've learned Git and the key elements of the "GitHub Flow" there are still more fun things to learn:

- Make some of those Git actions even simpler and more tightly coupled to GitHub using GitHub's native clients.
- Learn GitHub Flavored Markdown to write great structured documentation.
- Start using Issues to track bugs and enhancements.
- Emoji: :+1::sparkles:
- Learn GitHub's keyboard shortcuts. Hint: start by pressing ```shift+?```.
- Take a look at ways to build great personal & project specific sites using GitHub Pages.
- And more!

I gave a presentation a few years ago about this, give it a look, but even better just go try it!

<script async class="speakerdeck-embed" data-id="84962320626001306b3a22000a8f9817" data-ratio="1.2994923857868" src="//speakerdeck.com/assets/embed.js"></script>

## Looking for More

- https://guides.github.com
- http://training.github.com/web/free-classes/
- https://www.youtube.com/user/github/githubtraining
