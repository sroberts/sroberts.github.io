---
layout: post
title: Maltego Transforms for the Lazy
---

![Maltego](/public/maltego.png)

> <i class="fa fa-comments-o fa-3x pull-left"></i> While I certainly didn't plan to release this post the same day Paterva released their latest update, [Maltego Chlorine](http://maltego.blogspot.com/2015/03/maltego-chlorine-is-ready-for-download.html), it's a happy coincidence. It's a great day to go download fresh Maltego hotness and start writing some transforms!

[Maltego](https://www.paterva.com/web6/products/maltego.php) is one of the most unusual tools in the information security space. While there are dozens of vulnerability scanners and piles of reversing tools, there's nothing else like Maltego short of spending [$$$](http://www.reactiongifs.com/r/make-it-rain-dollars.gif) on [Palantir](https://www.palantir.com/). If you're not familiar, check out [this _HakTip_ by Revision3 on Maltego 101](http://revision3.com/haktip/maltego-101-what-is-maltego/). Don't worry, I'll wait.

I've used Maltego for years to do infrastructure research and visualizing logs, but I wanted it to do more. I needed to start writing transforms. But where to get started? Transforms typically start two places: the Canari Framework or the MaltegoTransform-Python library. I started with the latter.

## MaltegoTransform-Python Based Transforms

The [MaltegoTransform-Python Library](https://github.com/sroberts/maltegotransform-python) (from here out called MTP) is a quick way to prototype Maltego transforms in [Python](https://www.python.org/). As a trade-off, this requires manual setup within Maltego and provides basically no redistribution. MTP doesn't address new entity types either. Still, in my mind this is the best place to get started and it makes writing usable transforms in 10 lines of Python a snap.

Each transform is a single Python script (either with a `main()` method or just a straight procedural script). A basic transform reads in an entity as a command line argument, creates a transform object, adds entities to the transform object, and returns the transform object as [XML](http://www.xml.com/). That's it.

### MaltegoTransform-Python Imports

<script src="https://gist.github.com/sroberts/628db01006cbaaff48ac.js"></script>

In typical [Python magic, a quick _import/from_](http://xkcd.com/353/) is all it takes to load the library from your Python path. I leave MaltegoTransform.py in the same directory as my transforms. Most of the time the __MaltegoTransform__ object is all you need since it automatically invokes the _MaltegoEntity_ class). The __MaltegoEntity__ can be useful in advanced cases, though.

### Setup Transform

<script src="https://gist.github.com/sroberts/055cebd200d047632c5f.js"></script>

For a basic transform, the magic happens in the _MaltegoTransform_ object. It represents the collection of entities (nodes for the graph theory types) that the transform creates.

### Add Entities

<script src="https://gist.github.com/sroberts/ce019b5f3e188ee1fd46.js"></script>

The whole idea of building a transform is taking the source entity (the entity you run the transform on) and _transforming_ it into some other connected entity. For example, you transform an IPv4Address using a reverse DNS look-up to a Domain entity. This can be _one entity transformed to one entity_ or _one entity transformed to many entities_.

### Transform Output

<script src="https://gist.github.com/sroberts/8ebedec40e75080f8741.js"></script>

At that point, you return the _MaltegoTransform_ and that's it. The _returnOutput_ method outputs the transform information as [XML](http://www.reactiongifs.com/r/y3PWaHz.gif).

<script src="https://gist.github.com/sroberts/0f370d357bc7ea73a9f9.js"></script>

Maltego translates the new XML data into new entities on the graph. That's a transform. And you didn't even have to touch any XML yourself.

### Exceptions

<script src="https://gist.github.com/sroberts/3112cd5385ad0cc4676a.js"></script>

Every so often, things go wrong and it's important to be able to let the user know. MTP supports transform exceptions, _addException_ & _returnOutput_, which work just like _addEntity_ & _returnOutput_.

## [FreeGeoIP Geolocation](http://freegeoip.net) Transform

All these pieces are great, but a full example helps. This transform takes an IPv4Address entity, requests the geolocation data from [FreeGeoIp.net](http://freegeoip.net), and returns a Location entity.

<script src="https://gist.github.com/sroberts/0f51855447189bb9e010.js"></script>

What does this look like?

![FreeGeoIP Transform example](/public/transform-example.gif)

__A couple of notes:__

- If you want to use this transform, you'll need the Python [Requests](http://docs.python-requests.org/en/latest/) library. You should have it installed anyway as a Python developer.
-  Make sure the [MaltegoTransform-Python library](https://github.com/sroberts/maltegotransform-python) is in the same directory as the freegeoip-geolookup.py script. It can't transform without it!
- If you want to use this transform in Maltego, (and of course you do) you'll have to [register the transform manually](http://dev.paterva.com/developer/system/local_transforms/registration.php). This is that _manual_ bit I mentioned above. It basically specifies what application to use to run the transform (_/usr/bin/python_ in this case) as well as a path to the transform script itself. It's confusing for a bit but makes sense after a time or two.

## Paterva's Developer Resources

On February 3rd, 2015, Paterva stood up a [Developers Portal](http://dev.paterva.com/developer/) with resources to help people get started. This jump-started my development and should be anyone's first stop (after this post of course) for basic as well as advanced topics. I hope the Paterva team keeps expanding this site, although it's already a wealth of knowledge.

## But what about...?

Other options exist if you want to build transforms. MTP is great for basic transforms and prototyping, but most transform writers will need some of the more advanced options.

### [Canari Framework](http://www.canariproject.com/)

> <i class="fa fa-quote-left fa-3x pull-left"></i> Canari is a rapid transform development framework for Maltego written in Python.

Billing itself as _the most advanced_ & _easy-to-use_, Canari is a framework for creating and distributing complex Maltego transform sets by eliminating much of the boilerplate. Canari supports a variety of programming languages for building transforms, custom entity creation, local and remote transforms (running transforms on a server instead of off your local machine), as well as distribution so a team of analysts can share them.

Creating packages of complex transforms has a lot going on, and that makes it difficult to be both _easy-to-use_ and _advanced_ at the same time. MTP is great for prototyping transforms; Canari isn't. MTP would be a terrible way to create polished packages for distribution; Canari excels at that. Neither one is better or worse. They are both ideal for different use cases. [SniffMyPackets](http://sniffmypackets.net/), a pcap analysis suite, and [Malformity](https://github.com/digital4rensics/Malformity), a malware analysis package, are ideal uses of Canari and powerful systems for any analyst.

### [TDS & Remote Transforms](http://www.paterva.com/web6/products/servers.php)

I have no idea? I don't have a TDS aside from the public one. If I was working with a bigger team, all using Maltego, I'd invest in one but for now my experience is too limited to speak to them. They make it easy for everyone to work off a unified set of transforms & packages, ease the need to manually setup lots of Maltego instances, and centralize credentials and API keys. Paterva provided [a great site to help developers make the most of remote transforms](http://www.paterva.com/web6/documentation/developer-tds.php). I can say I do use the public TDS hosted transforms for [PassiveTotal](http://www.passivetotal.com/) and they were easy to setup, wickedly fast, and highly useful.

### [Transform Hub](http://dev.paterva.com/developer/advanced/transform_hub.php)

The Transform Hub is one of banner features of the Chlorine release and will be game changing for a lot of users. Local transforms can be cumbersome and Canari improves that, but Transform Hub seeks to this even easier by including everything in Maltego itself. This makes it easy to install and configure transforms.

## Conclusion

Is this the absolute best way to build transforms? Probably not, but I did name this _Maltego Transforms for the Lazy_. This is a great way to prototype new transforms and go from 0 to demo as efficiently as possible. I've just started writing transforms and I'm already having success pulling data into Maltego I'd have never imagined. Go for it, and share what you build, there's a lot to build on.

## Useful Links

- [Paterva Developer Documentation](https://www.paterva.com/web6/documentation/developer.php)
- [Maltego Developers Portal](http://dev.paterva.com/developer/)
- [<i class="fa fa-file-pdf-o"></i> Maltego: Basic Python Library (Local Transforms)](http://dev.paterva.com/developer/downloads/BasicPythonLibrary(Local-Transforms)cheatsheet.pdf)
- [<i class="fa fa-file-pdf-o"></i> Maltego: Integration Options with Maltego3](http://dev.paterva.com/developer/downloads/IntegrationoptionswithMaltegov3.pdf)
- [Paterva.com: Maltego Developer Snippets](http://dev.paterva.com/developer/code_snippets/local_transforms.php)
- [Maltego Blog: Calling All Transform Writers! and Maltego Chlorine details! and MORE!](http://maltego.blogspot.com/2015/02/calling-all-transform-writers-and.html)
