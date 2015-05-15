---
layout: post
title: pbcopy & pbpaste
---

__pbpaste__ and __pbcopy__ give you direct access to the OSX clipboard from a shell and makes it easy to tie together data from GUI based apps with command line apps.

## <i class="fa fa-clipboard"></i> pbpaste

So say you use ⌘+c to copy something from a browser that you want to then feed through a commandline tool like [./jq](http://stedolan.github.io/jq/):

> $ pbpaste \| jq '.'

## <i class="fa fa-files-o"></i> pbcopy

The reverse also works:

> $ ifconfig \| pbcopy

And then I can paste that into any other app using ⌘+v.

## <i class="fa fa-compress"></i> Put it Together

One of the most common uses is to manipulate data using sed:

> $ pbpaste \| sed -e 's/foo/bar/g' \| pbcopy

These two commands, like most Unix style commands, seems super basic. They're deceptively simple, but combined with other CLI tools pbpaste & pbcopy can create powerful combinations that simplify all kinds of tasks.
