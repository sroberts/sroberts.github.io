---
layout: post
title: Travel OpSec
---

Last year I was lucky enough to go to the [FIRST2015](https://www.first.org/conference/2015) conference in Berlin. It was a great conference, good talks (including [yours truly](http://sroberts.github.io/2015/07/08/ccir-presentation/)), and an even better hallway track. I'd never been to Berlin, or Germany in general, and I enjoyed seeing this amazing city a little bit as well.

Traveling to a new country as a security minded person is always a bit jarring. Even a country as friendly as Germany bares consideration when it comes to laptops, tablets, phones, etc. A conference like FIRST has people coming from all over the place, including people from countries at odds (US, China, Iran, Germany, etc). As a result those IT security concerns are even more heightened. As a result we ended up having some academic conversations about operational security while traveling internationally (or traveling generally).

## <i class="fa fa-angle-right"></i> The Challenges

Traveling internationally has some unique challenges compared to using IT resources at home.

### <i class="fa fa-plug"></i> Power
Running around a new country one of the first things you might notice is powering your devices can be tricky. Plugs are different, voltages are different, and you may not have the right adapters. A good [travel battery can help](http://www.amazon.com/Anker-9600mAh-Portable-External-Technology/dp/B00DMWV3EU/ref=sr_1_4?ie=UTF8&qid=1436634357&sr=8-4&keywords=battery+anker), but at some point you'll be hunting for an outlet to grab a charge.

### <i class="fa fa-wifi"></i> Network
Home is where the wifi is, but when you're traveling you have to take what you can get. You have to balance security with the need to connect. Random coffeeshop/airplane/hotel wifi are all viable pipes, but under who's control?

### <i class="fa fa-bicycle"></i> Movement

You're in an [exotic](http://www.lonelyplanet.com/montenegro/bay-of-kotor) (or maybe [not so exotic](http://toledo.oh.gov/)) place and you want to get out and see it. Go out to dinner, site seeing, etc. You'll want the freedom to do that, and you can limit yourself by how much you feel the need to carry.

## <i class="fa fa-angle-right"></i> The Threat

The first question for security should always be "What is the threat?". If you're basing your security stance on anything but practical threats then it's just FUD. While people exaggerate threats often in this case their seems to be plenty of concerns.

### <i class="fa fa-angle-double-right"></i> Seizure at Checkpoints & _Evil Maid_ Style Attacks

Depending on the country customs __seizing devices at check points__, either for minutes or days, may happen a little or may happen a lot. [But it does happen.](http://www.wired.com/2010/11/hacker-border-search/) A close relative of checkpoint seizure is the __evil maid__ attack, where someone with access (like a cloned keycard) enters your hotel and accesses your devices while you're out of the room (Oh, and they might also have cameras + listening devices in your room as well, just in case you fall into a honeypot).

The basic formula of both of these attacks is _physical access + time = compromise_.  Full Disk Encryption helps, but it's [not bulletproof](https://nakedsecurity.sophos.com/2012/02/02/filevault-encryption-broken/) given near infinite computing resources and near infinite time. If your computer leaves your site at a checkpoint assume the data is staying.

### <i class="fa fa-angle-double-right"></i> _Dark Hotel_ Style Attacks

Moving past physical attacks there are other ways to steal data in hotels. The [DarkHotel APT group](https://securelist.com/blog/research/66779/the-darkhotel-apt/
) __targets victims by compromising the networks of common traveler destinations__ such as international hotels and uses their access to infect victims with trojans, pilfering data at their convenience.

### <i class="fa fa-angle-double-right"></i> [Buckshot Yankee](http://www.washingtonpost.com/wp-dyn/content/article/2010/08/24/AR2010082406495.html) & [Stuxtnet Style USB Attacks](http://www.wired.com/2014/11/countdown-to-zero-day-stuxnet/) + Accidental Syncing

Power seems at most partially related to security, but USB based charging is common for tablets and phones even laptops. For certain advanced attack groups __USB device attacks are a way to compromise offline devices__. Plugging a device into a USB charging dock in an airport or into a new friends laptop is an easy way to get an extra 10% power, but risks picking up malware or syncing your mobile device and handing over all the data on it.

### <i class="fa fa-angle-double-right"></i> Theft & Loss

Simple and boring but no less real, IT resources get lost all the time. Cell phones get left in cabs, laptops get stolen in cafes, all happen, and all pose a risk. It's hard to stay backed up on the go and it can be extra difficult to recover these devices on foreign soil.

### <i class="fa fa-angle-double-right"></i> Lastly... [The Honeypot](http://cdn.meme.am/instances/63396171.jpg)

I'm not going into this one, but [it happens](https://en.wikipedia.org/wiki/Clandestine_HUMINT_asset_recruiting#Love.2C_honeypots.2C_and_recruitment).

## <i class="fa fa-angle-right"></i> The Plan: Rules for International Travel OpSec

So now that we're clear on the challenges & threats, at least the big ones, lets discuss the solutions.

### <i class="fa fa-globe"></i> International Travel Rule #1: LEAVE IT AT HOME!!!

I cannot emphasize this enough. If you don't have it with you it cannot be compromised, the data cannot be stolen, and you don't have to worry about it. Far and away leaving it at home is the lowest risk approach. For alternatives where you need to take your laptop see step #2 but prepare yourself: These things are a pain. They're difficult. And they must be.

### <i class="fa fa-globe"></i> International Travel Rule #2: Prep It Before You Leave

You actually have to take a laptop? Are you sure? Well if I can't convince you otherwise at least be cautious. An ounce of prevention is worth a pound of cure, so take some time to get things ready.

#### <i class="fa fa-angle-double-right"></i> Loaners & Alternatives

Borrower laptops are a common approach and are certainly better than taking your usual laptop but I'm still not crazy about them. While they may limit exposure they have three failings:

1. To make them useful they still get loaded up with some (if limited) data (the whole thing we want to avoid).
2. They aren't inherently harder to compromise than the users own laptop.
3. Since they aren't the users _own system_ the user is often less careful with it, resulting in risk.

To this end the CrowdStrike team released some of their [scripts for setting up an ArchLinux laptop for travel](https://github.com/CrowdStrike/travel-laptop) which looks like an solid solution for setting up loaner laptops.

I'm a far bigger fan of devices like an [iPad](http://www.apple.com/ipad/) or [Chromebook](http://www.dell.com/us/business/p/chromebook-11/pd?oc=cacb003&model_id=chromebook-11&l=en&s=bsd) for travel. They're easy to wipe & reset, don't store much data, designed to resist attack, and cheaper than a full laptop.

![Chromebook](https://storage.googleapis.com/hw-chromebooks/Samsung%20Chromebook%202/gallery-SamsungChromebook211-1-card-F101_SamsungChromebook211_SILVER.jpg)

They're also both super light and get great battery life. All but the most dedicated road warriors don't need more than a browser for most travel use anyway.

#### <i class="fa fa-angle-double-right"></i> Patch Everything
Everything... and then double check:

- Operating System
- Applications (Focus on the applications you use every day and common vector apps like Adobe Acrobat & Reader, Microsoft Office, Flash, your browser (or just switch to Chrome and update that))
- Secondary tools (Like Browser plugins)

Don't forget your "other" devices like phones, Kindles, etc.

#### <i class="fa fa-angle-double-right"></i> Prepare 2FA

![Yubikey](/public/yubikeys.jpg)

You already have two factor authentication turned on every where you can right? Well double check and make sure. [TOTP](https://tools.ietf.org/html/rfc6238) based is great, but [YubiKey](https://www.yubico.com/products/yubikey-hardware/) is becoming even more attractive as services are beginning to support the [FIDO/U2F standard](https://www.yubico.com/applications/fido/). I'm also a big [DuoSecurity](https://www.duosecurity.com/) fan for it's great interface, easy integration, and reasonable prices.

#### <i class="fa fa-angle-double-right"></i> Setup a VPN

[Setting up your own VPN isn't that hard](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-14-04) and provides a lot of trust and flexibility, even if it comes with some extra effort. While you're at it take the time to [enable DuoSecurity](https://www.duosecurity.com/docs/openvpn) as well.

[![Cloak](/public/cloak.jpg)](https://www.getcloak.com/)

You could also use a paid VPN provider. The downside is placing your trust in another service but the upside is it's easy and often comes with more polish. I like [Cloak](https://www.getcloak.com/) for it's clean design and multi-device support.

#### <i class="fa fa-angle-double-right"></i> Privacy Screen Cover

[3M makes some nice privacy screen covers](http://solutions.3m.com/wps/portal/3M/en_EU/Protectors/Home/). I have one and it's great.

![IT GOLD!!!!](/public/3mfilter.jpg)

Pretty huh? That said I'm still mixed on them. While it does a great job of keeping your words from the person sitting next to you it also draws attention. People wonder what you're trying to hide which makes it a double edged sword. Avoiding the gold side helps.

#### <i class="fa fa-angle-double-right"></i> USB "Condom"
Charging USB devices off of random USB charging stations or someone elses laptop is convenient but runs the risk of exposing you to [USB transmitted malware](http://www.symantec.com/security_response/writeup.jsp?docid=2010-071400-3123-99) or accidental syncing.

![USB Condom](/public/syncstop.jpg)

A USB condom (sorry for the uncouth term Mom) protects you by breaking the data transfer connections of USB while leaving the power connections intact. That means you can charge your device without inadvertently syncing data or worse.

[SyncStop](http://syncstop.com/) makes a very nice device.

### <i class="fa fa-globe"></i> International Travel Rule #3: Be Aware of your Surroundings

I don't know how to suggest how you do this, but you need to do it. That's not super helpful, [so I'm doing what anyone does, Googling it](http://bfy.tw/3oW0). I recommend reading this [article from Psychology Today on Becoming Aware](https://www.psychologytoday.com/blog/pathological-relationships/201206/becoming-aware). If that isn't ninja enough for you I suppose you may want to read [the articles tagged "How To Become Aware of Your Surroundings" from the WayOfNinja](http://wayofninja.com/tag/how-to-become-aware-of-your-surroundings/) but I don't recommend it.

### <i class="fa fa-globe"></i> International Travel Rule #4: Carry Your Devices with you At All Times

I told you this would be a pain. This basically goes directly against the _mobility_ concept we started out with, but it turns out it's highly important. Two of the threat types we discussed require physical access and the way to be sure is to have them with you at all times.

That doesn't mean except for dinner. That doesn't mean unless you want to go for a walk. __Always.__ I recommend getting [a bag you find comfortable for long periods of time](http://www.dsptch.com/collections/packs/products/tech-messenger-navy), the lightest devices possible (or, you know, just leave it at home like I suggested in the first place). Which devices do you need to carry? My rule of thumb: if it has a USB port or network access you can't leave it.

> <i class="fa fa-comment"></i> _Note:_ This doesn't make physical attacks impossible, it just makes it impossible for you to not be aware. You're not a [SERE school](https://en.wikipedia.org/wiki/Survival,_Evasion,_Resistance_and_Escape) grad (unless you are in which case good for you) and if someone wants to take your devices they will. At least you'll be aware and able to tell your security team what happened.

### <i class="fa fa-globe"></i> International Travel Rule #5: Keep Things Turned Off & Logged Out

Once you rule out physical access the only attack vectors are Wifi, Bluetooth, etc. It's inconvenient but it works wonders, otherwise you may find yourself randomly connecting to unknown Bluetooth devices or wireless networks. This goes double for borders.

## <i class="fa fa-angle-right"></i> Extreme Hardening

So lets say for some reason you really, actually, insistently must take a full on laptop to a foreign country. To make matters worse it's one that's passive aggressively hostile towards yours. Well in that case you'll want to do some serious system hardening. Your goal is to remove as much attack surface as possible and beef up the things you must have exposed. I mostly use OSX, so here are a couple of the better hardening guidelines for Macbooks:

- <i class="fa fa-list-ol"></i> [Harden the World: Mac OSX 10.11 El Capitan](http://docs.hardentheworld.org/OS/OSX_10.11_El_Capitan/)
- <i class="fa fa-list-ol"></i> [GitHub: drduh/OS-X-Security-and-Privacy-Guide](https://github.com/drduh/OS-X-Security-and-Privacy-Guide)

There's also this lock-down tool by the always awesome [Scott Piper](https://twitter.com/0xdabbad00):

- <i class="fa fa-wrench"></i> [GitHub: SummitRoute/osxlockdown](https://github.com/SummitRoute/osxlockdown)

I haven't used Windows for years, but I know [EMET](https://www.microsoft.com/en-us/download/details.aspx?id=50766) is pretty great (I'd love to see an EMET like kit for OSX) and Microsoft has invested a lot into making Windows 8 & 10 hard targets. For anything else I'd take a look at DISA's [Security Technical Implementation Guidelines](http://iase.disa.mil/stigs/Pages/index.aspx) or the NSA/CSS [Security Configuration Guides for Operating Systems](https://www.nsa.gov/ia/mitigation_guidance/security_configuration_guides/operating_systems.shtml).

## <i class="fa fa-angle-right"></i> Conclusion

This is far from a comprehensive guide to safe traveling. The world is a dangerous place. Hopefully though this gives you some ideas on how to level up your IT security while traveling. The world is an amazing place, I've been lucky to see as much of it as I have and I can't way to see more, but a little consideration goes a long way.

And one last time: ___Just leave your laptop at home. You'll be fine.___ And you might experience something amazing.

_If you want to go further I recommend reading [Jeffrey Carr's A Traveler's Guide to Cyber Security](http://www.amazon.com/A-Travelers-Guide-Cyber-Security-ebook/dp/B007GYLMQE))._
