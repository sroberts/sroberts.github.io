---
layout: post
title: Travel OpSec
---

I spent the middle of June attending the FIRST 2015 conference in Berlin. This was a great conference, good talks (including yours truely) and an even better hallway track. I'd never been to Berlin, or Germany in general, and I enjoyed seeing this amazing city a little bit as well.

Travelling to a new country as a security minded person is always a bit jarring. Even a country as friendly as Germany bares consideration when it comes to laptops, tablets, phones, etc. FIRST has people coming from all over the place, including people from countries at odds (US, China, Iran, Germany, etc). As a result those IT security concerns are even a little more hightend. As a result we ended up having some academic conversations about operational security while traveling internationally, and is a worthwhile consideration.

## <i class="fa fa-angle-right"></i> The Challenges

Traveling internationally has some unique challenges compared to using IT resources at home.

### <i class="fa fa-plug"></i> Power
Running around a new country one of the first things you might notice is powering your devices can be tricky. Plugs are different, voltages are different, and you may not have the right adapters. A good [travel battery can help](http://www.amazon.com/Anker-9600mAh-Portable-External-Technology/dp/B00DMWV3EU/ref=sr_1_4?ie=UTF8&qid=1436634357&sr=8-4&keywords=battery+anker), but at some point you'll be hunting for an outlet to grab a charge.

### <i class="fa fa-wifi"></i> Network
Home is where the wifi is, but when you're traveling you have to take what you can get. You have to balance security with the need to connect. Random coffeeshop/airplane/hotel wifi all are viable pipes, but under who's control?

### <i class="fa fa-bicycle"></i> Movement

You're in an exotic (or maybe not so exotic) place and you want to get out and see it. Go out to dinner, site seeing, etc. You'll want the freedom to do that, and you can limit yourself by how much you feel the need to carry.

## <i class="fa fa-angle-right"></i> The Threat

The first question for security should always be "What is the threat?". If you're basing your security stance in any regard on anything but practical threats. While we exhagerate threats often in this case their seems to be plenty of concerns.

### <i class="fa fa-angle-double-right"></i> Seizure at Checkpoints

Depending on the country it may happen a little or may happen a lot. [But it does happen.](http://www.wired.com/2010/11/hacker-border-search/) Given the formula that _physical access + time = compromise_ it's a valid concern. FDE helps, but it's [not bulletproof](https://nakedsecurity.sophos.com/2012/02/02/filevault-encryption-broken/) given near infinite computing resources and near infinite time. If your computer leaves your site at a checkpoint assume the data is staying.

### <i class="fa fa-angle-double-right"></i> _Evil Maid_ Style Attacks

A close relative of checkpoint seizure is the __evil maid__ attack, where someone with access (like a cloned keycard) enters your hotel and accesses your devices while you're out of the room. This coupled with a little physical survailence (to know when you're headed back) gives an attacker an unharassed time to riffle through your devices, paperwork, etc. Oh, and they might also have cameras + listening devices in your room too, just in case you fall into a honeypot.

### <i class="fa fa-angle-double-right"></i> _Dark Hotel_ Style Attacks

<iframe width="560" height="315" src="https://www.youtube.com/embed/HQpGzivvtqg" frameborder="0" allowfullscreen></iframe>

Moving past physical attacks there are other ways to steal data in hotels. The [_DarkHotel_ APT group](https://securelist.com/blog/research/66779/the-darkhotel-apt/
) targets victims by compromising the networks of common traveler destinations such as international hotels and uses their acces to infect victims with trojans, pilfering data at their convenience.

### <i class="fa fa-angle-double-right"></i> [Buckshot Yankee](http://www.washingtonpost.com/wp-dyn/content/article/2010/08/24/AR2010082406495.html) & [Stuxtnet Style USB Attacks](http://www.vanityfair.com/news/2011/04/stuxnet-201104) + Accidental Syncing

Power seems at most partially related to security, but USB based charging is common for tablets and phones (even the new Apple MacBook & Chromebook Pixel) . It's also one of the more insidious ways to compromise offline devices. Plugging a device into a USB charging dock in an airport or into a new friends laptop is an easy way to get an extra 10% power, but risks picking up malware or syncing your mobile device and handing over all the data on it.

### <i class="fa fa-angle-double-right"></i> Theft & Loss

Simple and boring but no less real, IT resources get lost all the time. Cell phones left in cabs, laptops stolen in cafes, all happen, and all pose a risk. It's hard to stay backed up on the go and it can be extra difficult to recover these devices in a foreign country.

### <i class="fa fa-angle-double-right"></i> Lastly... The Honeypot

I'm not going into this one, but [it happens](https://en.wikipedia.org/wiki/Clandestine_HUMINT_asset_recruiting#Love.2C_honeypots.2C_and_recruitment).

## <i class="fa fa-angle-right"></i> The Plan: Rules for International Travel OpSec

### <i class="fa fa-globe"></i> International Travel Rule #1: LEAVE IT AT HOME

I cannot emphasize this enough. If you don't have it with you it cannot be compromised, the data cannot be stolen, and you don't have to worry about it. It is far and away the safest approach.

### <i class="fa fa-globe"></i> International Travel Rule #2: Prep It Before You Leave

You actually have to take a laptop?? Are you sure? Well if you can't be convinced otherwise at least do it as safely as possible.

#### <i class="fa fa-angle-double-right"></i> Loners & Alternatives

Borrower laptops are often one approach, though I'm not crazy about them. While they may limit how much data is exposed they still have three failings:

1. To make them useful they still get loaded up with some (if limited) data (the whole thing we want to avoid).
2. they aren't inheriently harder to compromise than the users own laptop
3. Since they aren't the users _own system_ the user is likely to be less careful with it, resulting in risk.

I'm a far bigger fan of devices like my [iPad](http://www.apple.com/ipad/) or [Chromebook](http://www.dell.com/us/business/p/chromebook-11/pd?oc=cacb003&model_id=chromebook-11&l=en&s=bsd) (especially the Chromebook) for travel. They're easy to wipe & reset, designed to resist attack, and cheaper than a full laptop. They're also both super light and get great battery life. All but the most dedicated road warriors don't need more than a browser for most travel use anyway.

#### <i class="fa fa-angle-double-right"></i> Patch Everything
Everything... and then double check:

- Operating System
- Applications (Focus on the applications you use every day and common vector apps like Adobe Acrobat & Reader, Microsoft Office, Flash, your browser (or just switch to Chrome and update that))
- Secondary tools (Like Browser plugins)

Don't forget your "other" devices like phones, Kindles, etc.

#### <i class="fa fa-angle-double-right"></i> Setup a VPN

[Setting up your own VPN isn't that hard](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-14-04) and provides a lot of trust and flexibility, even if it comes with some extra effort. While you're at it take the time to [enable DuoSecurity](https://www.duosecurity.com/docs/openvpn) as well.

Alternatively you could use a paid VPN provider. The downside is placing your trust in another service but the upside is it's easy and often comes with more polish. I like [Cloak](https://www.getcloak.com/) for it's clean design and multi-device support.

#### <i class="fa fa-angle-double-right"></i> Prepare 2FA

You already have two factor authentication turned on every where you can right? Well double check and make sure. [TOTP](https://tools.ietf.org/html/rfc6238) based is great, but [YubiKey](https://www.yubico.com/products/yubikey-hardware/) is becoming even more attractive as services are beginning to support the [FIDO/U2F standard](https://www.yubico.com/applications/fido/). I'm also a big [DuoSecurity](https://www.duosecurity.com/) fan for it's great interface, easy integration, and reasonable prices.

#### <i class="fa fa-angle-double-right"></i> Privacy Screen Cover

[3M makes some nice privacy screen covers](http://solutions.3m.com/wps/portal/3M/en_EU/Protectors/Home/). I have one and it's great.

![IT GOOOOOOLD!!!!](/public/3mfilter.jpg)

Pretty huh? That said I'm still mixed on them. While it does a great job of keeping your words from the peorson sitting next to you it also draws attention. People wonder what you're trying to hide. Avoiding the gold side helps.

#### <i class="fa fa-angle-double-right"></i> USB "Condom"

I feel a bit uncouth using that term, but it's the most common term. Sorry if you read this mom.

Charging USB devices wherever you happen to be, including off of USB charging stations or someone elses laptop is convenient, but runs the risk of exposing you to USB transmited malware. A USB condom protects you by breaking the data transfer connections of USB while leaving the power connections intact. That means you can charge your device without inadvertently syncing data or worse.

![USB Condom](http://cdn.shopify.com/s/files/1/0616/6813/products/IMG_1204_grande.JPG?v=1432758676)

I have one from [SyncStop](http://syncstop.com/) that's great.

### <i class="fa fa-globe"></i> International Travel Rule #3: Be Aware of your Surroundings

### <i class="fa fa-globe"></i> International Travel Rule #4: Keep Things Turned Off & Logged Out

Wifi, Bluetooth, etc. It's inconvinet but it works wonders, otherwise you may find yourself randomly connecting to .

## Conclusion

## Resources
- Jeffery Carr's Book
- Dark Hotel Report
- Stuxtnet & Buckshot Yankee Reports
