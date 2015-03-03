---
layout: post
title: Maltego Transforms for the Lazy
---

![Maltego](/public/maltego.png)

Maltego is one of the most unique tools in the information security space. While there are dozens of vulnerability scanners and piles of reversing tools there's nothing else like Maltego (short of spending [$$$](http://www.reactiongifs.com/r/make-it-rain-dollars.gif) on Palantir). If you're not familiar check out [this _HakTip_ by Revision3 on Maltego 101](http://revision3.com/haktip/maltego-101-what-is-maltego/). Don't worry, I'll wait.

 I've used Maltego for years to do infrastucture research and visualizing logs, but I wanted it to do more. I needed to start writing transforms. But where to get started? Transforms typically start two places: the [Canari Framework](http://www.canariproject.com/) or the [MaltegoTransform-Python library](https://github.com/sroberts/maltegotransform-python). We'll start with the latter.

## Transform Pieces

The MalgetoTransform-Python Library (from here out called MTP) is a quick way to prototype Maltego transforms in Python. The tradeoff is setup within Maltego is manual and redistribution is basically nil. MTP doesn't address new entity types either. Still in my mind the best place to get started and makes writing usable transforms in a 10 lines of Python a snap.

Each transform is a single Python script (either with a Main method or just a straight procedural script). A basic transform reads in an entity as a commandline arguement, creates a transform object, adds entities to the transform, and returns the transform object. That's it.

### MaltegoTransform-Python Imports
<script src="https://gist.github.com/sroberts/628db01006cbaaff48ac.js"></script>

In typical Python magic a quick _import/from_ is all it takes to load the library from your Python path (I leave it in the same directory m ost of the time). Most of the time the __MaltegoTransform__ object is all you need (it automatically invokes the _MaltegoEntity_ class), but the __MaltegoEntity__ can be useful in advanced cases.

### Setup Transform
<script src="https://gist.github.com/sroberts/055cebd200d047632c5f.js"></script>

For a basic transform the _MaltegoTransform_ object is where the magic happens. It represents the collection of entities (nodes for the graph theory types) that the transform creates.

### Add Entites
<script src="https://gist.github.com/sroberts/ce019b5f3e188ee1fd46.js"></script>

The whole idea of building a transform is taking the source entity, the entity you run the transform on, and _transforming_ it into some other connected entity. For example transforming an IPv4Address (using a reverse DNS lookup) to a Domain entity. This can be a _1 to 1_ or _1 to Many_ action.

### Transform Output
<script src="https://gist.github.com/sroberts/8ebedec40e75080f8741.js"></script>

At that point you return the MaltegoTransform and that's it. The _returnOutput_ method outputs the transform information as XML.

<script src="https://gist.github.com/sroberts/0f370d357bc7ea73a9f9.js"></script>

Maltego translates into new XML data into new entites on the graph. Thats a transform.

### Exceptions
<script src="https://gist.github.com/sroberts/3112cd5385ad0cc4676a.js"></script>

Every so often things go wrong and it's important to be able to let the user know. MTP supports transform exceptions, _addException_ & _returnOutput_, which work just like _addEntity_ & _returnOutput_.

## [FreeGeoIP Geolocation](http://freegeoip.net) Transform

All these pieces are great, but a full example helps. This transform takes an IPv4Address entity, requests the geolocation data from [FreeGeoIp.net](http://freegeoip.net), and returns a Location entity.

<script src="https://gist.github.com/sroberts/0f51855447189bb9e010.js"></script>

__A couple notes:__

- If you want to use this transform you'll need the Python [Requests](http://docs.python-requests.org/en/latest/) library. You should have it installed anyway as a Python developer.
-  Make sure the [MaltegoTransform-Python library](https://github.com/sroberts/maltegotransform-python) is in the same directory as the freegeoip-geolookup.py script. It can't transform without it!
- If you want to use this transform in Maltego (and of course you do) you'll have to [register the transform manually](http://dev.paterva.com/developer/system/local_transforms/registration.php). This is that _manual_ bit I mentioned above. It's basically specifying what application to use to run the transform, _/usr/bin/python_ in this case, as well as a path to the transform script itself. It's confusing for a bit but makes sense after a time or two.

## Patervas Developer Resources

On February 3rd Paterva stood up a [Developers Portal](http://dev.paterva.com/developer/) with resources to help people get started.

## But what about...?

There are other options if you want to build transforms. MTP is great for basic transforms and prototyping, but most transform writers will need some of the more advanced options.

### Canari

> <i class="fa fa-quote-left fa-3x pull-left"></i> Canari is a rapid transform development framework for Maltego written in Python.

Billing itself as _the most advanced_ & _easy-to-use_ Canari is a framework for creating and distrubting complex Maltego transform sets by eliminating much of the boilerplate. Canari supports multiple programing langauges for building transforms, entity creation, local and remote Transforms (running Transforms on a server instead of off your local machine), as well as distribution so multiple analyts can share them.

When I began looking into transform development I started by looking at Canari and found it difficult to wrap my head around. There's a lot going on to create packages of complex transforms and that makes it difficult to be both _easy-to-use_ and _advanced_ at the same time. MTP is great for prototyping transforms, Canari wasn't. MTP would be a terrible way to create polished packages for distribution, and Canari excels at that. Neither one is better or worse, they are both ideal for different use cases. [SniffMyPackets](http://sniffmypackets.net/), a pcap analysis suite, and [Malformity](https://github.com/digital4rensics/Malformity), a malware analysis package, are ideal uses of Canari and powerful systems for any analyst.

### [TDS & Remote Transforms](http://www.paterva.com/web6/products/servers.php)

I have no idea? I don't have a TDS aside from the public one. If I was working with a bigger team, all using Maltego, I'd invest in one but for now my experience is too limited to speak to them. They make it easy for everyone to work off a unified set of transforms & packages, ease the need to manually setup lots of Maltego instances, and centralize credentials and API keys.

## Useful Links

- [Maltego Developers Portal](http://dev.paterva.com/developer/)
- [<i class="fa fa-file-pdf-o"></i> Maltego: Basic Python Library (Local Transforms)](http://dev.paterva.com/developer/downloads/BasicPythonLibrary(Local-Transforms)cheatsheet.pdf)
- [<i class="fa fa-file-pdf-o"></i> Maltego: Integration Options with Maltego3](http://dev.paterva.com/developer/downloads/IntegrationoptionswithMaltegov3.pdf)
- [Paterva.com: Maltego Developer Snippets](http://dev.paterva.com/developer/code_snippets/local_transforms.php)
- [Maltego Blog: Calling All Transform Writers! and Maltego Chlorine details! and MORE!](http://maltego.blogspot.com/2015/02/calling-all-transform-writers-and.html)
