---
layout: post
title: Installing Yara 2 on Ubuntu 14.04
---

One of my projects this weekend is getting [Cuckoo Sandbox](http://cuckoosandbox.org/) stood up again. I hadn't done much more than beginning to install libraries and dependencies than it called for one of my favorite security tools: [Yara](http://plusvic.github.io/yara/).

In the past I was a heavy Yara user, but I haven't really played with it much since the upgrade to 2.0. Version 2 includes some big improvements and Yara is a valuable tool alone as well as in conjunction with a tool like Cuckoo. That said, [Ubuntu](http://www.ubuntu.com/) out of the box is pretty sparse out of the box and the included but hard to find instructions for installing Yara don't include much information about prerequisites.

Here's the process I followed:

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python libtool automake autoconf python-dev
```

I downloaded the most recent release:

```wget https://github.com/plusvic/yara/archive/2.1.0.tar.gz```

At this point I followed through with the given instructions:

```
tar -zxf yara-2.1.0.tar.gz
cd yara-2.1.0
./build.sh
sudo make install
```

Things seemed fine, I tried running ```yara -h```.

```
cuckoo@cuckoo-box:~/yara-2.1.0$ yara
yara: error while loading shared libraries: libyara.so.2: cannot open shared object file: No such file or directory
```

Well that's frustrating:

![](http://www.reactiongifs.com/wp-content/uploads/2013/12/sherlock-frustrated.gif)

Not a normal error, but a quick Google for ```error loading shared libraries``` led to a [Stack Overflow article named "Error loading shared libraries"](http://stackoverflow.com/questions/4514997/error-loading-shared-libraries). Well isn't that lucky? Turns out just running ```sudo ldconfig``` tracked down my missing shared object, and next thing I know:

```
cuckoo@cuckoo-box:~$ yara
usage:  yara [OPTION]... RULES_FILE FILE | PID
options:
  -t <tag>                 only print rules tagged as <tag>.
  -i <identifier>          only print rules named <identifier>.
  -n                       only print not satisfied rules (negate).
  -g                       print tags.
  -m                       print metadata.
  -s                       print matching strings.
  -p <number>              use the specified <number> of threads to scan a directory.
  -l <number>              abort scanning after matching a number rules.
  -a <seconds>             abort scanning after a number of seconds has elapsed.
  -d <identifier>=<value>  define external variable.
  -r                       recursively search directories.
  -f                       fast matching mode.
  -w                       disable warnings.
  -v                       show version information.

Report bugs to: <vmalvarez@virustotal.com>
```

## For the Mac Users

If, on the other hand, you're just looking to use Yara on your OSX client and you happen to be a [Homebrew](http://brew.sh/) user (and why wouldn't you be?) then you can just use ```brew install yara```.
