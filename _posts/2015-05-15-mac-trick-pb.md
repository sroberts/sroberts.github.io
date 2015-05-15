---
layout: post
title: pbcopy & pbpaste
---

__pbpaste__ & __pbcopy__ give you direct access to the OSX clipboard from a shell and makes it easy to tie together data from GUI based apps with command line apps.

## <i class="fa fa-clipboard"></i> pbpaste

So say you use ⌘+c to copy something from a browser that you want to then feed through a command line tool like [./jq](http://stedolan.github.io/jq/):

> $ pbpaste \| jq '.'

pbpaste feeds the text from the clipboard to jq through standard in, which then allows jq to manipulate it as you see fit. The result gets sent to standard out (or wherever the second tool sends it).

## <i class="fa fa-files-o"></i> pbcopy

The reverse also works:

> $ cat file.txt \| pbcopy

pbcopy takes data from standard in and saves it to the OSX clipboard. You can paste that into any other app using ⌘+v. This is great for grabbing the contents of files without having to open them in another application.

## <i class="fa fa-compress"></i> Put it Together

One of the most common uses is to manipulate data using sed:

> $ pbpaste \| sed -e 's/foo/bar/g' \| pbcopy

These two commands, like most Unix style commands, seem super basic. They're deceptively simple and combined with other CLI tools pbpaste & pbcopy can create powerful combinations that simplify all kinds of tasks.
