---
layout: post
title: The What happens when you use a browser Question
---

![Browser Bar](https://cdn-images-1.medium.com/max/2000/1*t0K-Euhu84XWzQphx5WvHA.png)

Go into a tech interview, especially one for operations or security, and you’re more than likely going to get an interview question like this:

> “What happens when you put a URL in the address bar of a browser and hit enter?”

I’ve been on both ends of this question, asked it and answered it. I’d like to look at what the answer is (or at least one answer), why it’s good, why it’s bad, and what could be better.

## My Answer

Like many good things in life the answer to this question is a recipe in two parts.

![Cooking!](https://media.giphy.com/media/26AHKESympDDgNG24/giphy.gif)

Well… it’s sorta cooking… Source: [Giphy](https://giphy.com/gifs/budweiser-summer-beer-burger-26AHKESympDDgNG24)

### The Ingredients

There are concepts/acronyms you must know, name drop, and discuss:

- [OSI: Open Systems Interconnect Model](https://support.microsoft.com/en-us/kb/103884)
- [DNS: Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)
- [BGP: Border Gateway Protocol](https://en.wikipedia.org/wiki/Border_Gateway_Protocol)
- [HTTP: Hypertext Transfer Protocol](https://www.w3.org/Protocols/)
- [TLS & HTTPS: Encrypted HTTP](https://tools.ietf.org/html/rfc5246)

### The Recipe

Those ingredients aren’t enough. You have to know how to put them together.

To start with there is all the stuff that happens on the client. This can go pretty deep pretty quickly, even getting into processor interrupts, how the key presses lead to the letters showing up on screen, etc. It’s a deep rabbit hole, so I avoid that idea to start by making a joke about it and moving on. Getting caught up in a systems architecture discussion just means this question lasts 15 mins instead of five. No one wants that.

![Internetting!](https://media.giphy.com/media/6GCZQskrmzl7i/giphy.gif)
_Literally how do you even Internet? Source: [Giphy](http://giphy.com/gifs/computers-6GCZQskrmzl7i)_

First real bit is jumping into a discussion of either the local network stuff like DHCP and switches or DNS. I’m split on the best move. DHCP and local networking stuff is boring but essential and lets you talk about the OSI model early. I make a quick reference that this is home network stuff (it is), ask if the asker really wants to go into that (they never have) and move on.

The Domain Name System is where I really start building up a head of steam. First I dive in with an every person description of DNS, describing it as a telephone book for the Internet, taking written names people understand and turning them into numbers that people are bad at, equating phone numbers to IP addresses. Elegant and simple. Too simple you say? Then I come right back with a deeply technical concept, discussing the recursive nature of DNS, how you check the local name server first and then it checks the next server up until you get to the root (pick a letter if your choosing, no one knows them that well), then reference the TLD server, and then down to a specific domain answer. Are you interviewing with a dotcom? This is a great place to throw in a “… but it wouldn’t go that far to get to your site, that would already be cached.” (You suck up you!) and then explain how DNS record caching works. Don’t hesitate to throw in an aside about round robin DNS for big sites… you don’t really have to explain it (unless its a DNS job) because your interviewer likely doesn’t know what it is either, they’ve just heard the network team mention it.

Now that we have an IP address we can move on to packets. Throw in the ol’ SYN, SYN/ACK, ACK TCP handshake bit (you already talked about UDP during DNS right? If you didn’t just throw it back in now). Next you’re talking about how packets get across the Internet. I’ll be honest, I don’t fully understand this myself and I really should. I know it involves the Boarder Gateway Protocol but even after being asked this question multiple times I heaven’t really learned how that works (I should). Why haven’t I? Well honestly just saying “Some BGP magic happens…” has always been enough. Once I even mentioned [RIP](https://en.wikipedia.org/wiki/Routing_Information_Protocol) and even though that’s totally out of date no one cared.

![NETWORKS GONNA NETWORK](https://media.giphy.com/media/l41YvpiA9uMWw5AMU/giphy.gif)

Does it mean anything? Naa… just looks cool. Source: [Giphy](http://giphy.com/gifs/technology-data-transfer-optical-fiber-l41YvpiA9uMWw5AMU)

Breeze past that and now your describing your packets once they’ve arrived. Throw in some sequence & acknowledgement numbers and reassembly, good to mention even if it’s stuff the networking stack does for you. Now we’re talking HTTP and basic conventions like serving the index.html page, but no one does that anymore, we’re into crypto now, in fact that’s part of why the question got asked, so pivot quickly to an URL redirect (mentioning HTTP code 3xx just because) and move on.

![XKCDFTW](https://cdn-images-1.medium.com/max/1600/1*0TiRTV4aOynEu6K9MIMQaA.png)

Source: [XKCD](https://xkcd.com/435/)

Alright the main event, this is where we’ve been going all this time, to explain that little green lock in the browser. Here you’ll want to start discussing public and private key cryptography, say something about super big prime numbers and move on. Math… who knows? You can shift this to certificates without a lot of pretense (it’s just some extra metadata right? No one really understands X509) and now you’re discussing chains of trust. This means discussing Certificate Authorities and how they sign other keys (Intermediate Certs) most of which are used to sign other keys until they get to your browser. Then some more magic happens and somehow the public key for the CA (stored in your browser already which is so handy), can be used to verify the public key of the site your on. How? I don’t know… big prime numbers? The point is it works and I haven’t done real math since college. Also add something about how certificates are tied to the domain name of the site, so that DNS thing is now doubly important.

Now you’re into the bonus round and you can mention lots of things. Some attack on CAs, sure. Dodgy CAs from some bad country, why not. Perfect forward secrecy, perfectly natural. What a browser does or should do when a certificate is wrong? Gutsy! Extended Validation, crypto deceleration, revocation, hash collisions, weak algorithms. The world is your oyster.

Is my answer good? Not really. I’m sure some networking centric folks will pick out real inaccuracies beyond me being flippant. I know they’re rampant. That isn’t the point though. The point is its good enough. The reason it’s good enough isn’t because my answer is correct but because ultimately the question itself is bad.

## Why Interviewers Like It

I don’t blame anyone for using this question. There are reasons it seems great and in many cases the interviewer doesn’t get a choice. To start with it’s a multilayer question that’s highly open ended. A skilled interviewer can use this question to pivot into a variety of concepts around networking, intrusion detection, cryptography, fraud & abuse, etc. It lets an interviewee cover lots of ground and focus on specific aspects they want. It also hits on topics most networking and security folks have a basic understanding of.

## Why It Isn’t A Good Diagnostic

First of all because it’s asked so often. I bet you’re thinking back to the last time you got it. It’s a question everyone can and should be prepared for. It’s also an answer that can come out of a book (or a well written blog post) and isn’t based on any practical experience. You study for about 30 mins and you can answer this question solidly, even without understanding what’s going on under the hood.

This question is deeply reliant on a skilled interviewer with deep understanding at all levels. While there are a few people capable of that (I was interviewed by one when I got my job at Mandiant) many people aren’t. Instead they just listen for a few key elements, probably 4 of the 6 ingredients mentioned above, and move on.

The result is an interviewer can’t judge an answer well because in most cases they don’t understand the question entirely either. They understand it just well enough to see someone who doesn’t know any of it but not well enough to argue with a vague or inaccurate answer. Truth be told almost no one should be expected to understand it all. Its too big, too wandering, and just understanding core concepts of the big pieces is difficult let alone a deep technical discussion at every layer. In the end all it does is test the ability to give a hand wavy conceptual answer about some common Internet subsystems. It doesn’t prove you can run any of them, troubleshoot any of them, or secure any of them.

__In short describing this process doesn’t prove you can do a network operations or network security job in the least.__

## What would be better?

I think there’s a wide variety of important questions that can fill the same role. A bit of decomposition helps a lot, both for focus and ease of developing realistic answers. Here are a few ideas for better questions:

> Describe how your home network is setup? What functions does it support? What decisions did you make about performance or security?

This gets away from mere facts and piles of acronyms and into uses and practical experience. Its subjective, open for discussion, and based on a users own experience.

> What’s the difference between TCP and UDP and what’s a good use for each?

I’ve used this question a lot and it is funny. It starts like a common book question and then takes a turn. I’ve actually had more than one interviewee explain to me why no one should ever use UDP.

> If you want to encrypt and compress a file which do you do first and why?

Its an academic question that doesn’t have an open ended answer, but it captures the understanding of basic cryptography concepts, at least to the level most people need to know them. Its also a good question for non-technical interviewers since it has a definitive answer.

> If setting up an intrusion detection system would you set it up on the inside of a firewall or the outside? Why?

A bit more security centric, this is open ended while still being far more finite.

Better than any of these in my personal opinion? Don’t ask a question and expect an answer that second. That rarely happens day to day and thus doesn’t test an interviewees ability to do the job. Go for realism. Give a scenario similar to what the interviewee would actually do in their job and give them a chance to work through it, even learn about it if they need to. Are they interviewing to analyze malware? Give them a sample and a report template to fill out. Will they work through logs? Have an ELK server while a few million logs and ask them to identify the right ones based on a scenario you’ve seen before. Don’t just see if an employee can answer questions, see if they can do the job by doing it. Then ask them about their process.

> We use <SNORT/YARA> and are currently very concerned about <NEW FUN THREAT>. Can you write us a signature for it? Here’s an example of what we’re trying to detect.

Not just an answer, now the response is an actual artifact that can be tested. Also real world applicable and lets you ask follow up questions about it.

Improving Interviews
There are plenty of other good questions and you should work up a list of them. More than that look at what your interview process is set to test for and make sure it aligns with the tasks the interviewee would face in their first day. Unless you’re starting a Network Traffic Trivia Team it probably won’t start with “What happens when you start typing in a browser?”.

<hr>

## Personal Aside: Culture Fit

This bit will be unpopular and may even bug folks, but I think if you’ve read this far it’s because you care about improving your technical interviews. __Let’s do away with culture fit questions.__

I admit I used to love asking these. They were fun and easy. My team wanted people we would get along with so we asked the following:

> If every time you walked into a room a song played like you were walking in for WWF what would it be?

I thought it was great, clever, funny, innocuous but now I see it a lot differently.

- First of all it implies you know what WWF is and how the walk in song works. Not everyone does.
- Second it puts someone on the spot to name a song, a pretty unexpected departure from questions about Snort and ArcSight. It’s totally out of left field.
- Thirdly it encourages the interviewee to given an answer they think the interviewer will like, not a song they like. Maybe the interviewee likes classical or jazz and isn’t into EDM or rock.
- It doesn’t speak to anything about the job, common tasks, or anything day to day. Unrelated in the extreme.
- Lastly by its very nature it implies a certain arrogance and bravado that not everyone has and honestly you might not want in a coworker (and I hesitate to think what liking the question implied about 26 year old me…).

I’m embarrassed I used to ask that question. I can’t say I’ve ever been given a culture fit question that was a better diagnostic than an our question (an investment bank I once interviewed with might be the one exception but that may not be an especially good thing) and at this point I’m adamantly against them. _I get that no one likes working with a jerk, but determining that takes more than asking someone’s outside interests._

__Culture fit questions, by their very nature, focus on finding other people just like the interviewer.__ That’s fine if you’re interviewing for a new best friend, but for a professional setting your focus shouldn’t be on someone who likes the same movies or weekend activities, it should focus on someone who can do the job. Culture fit questions also disproportionately select against diverse candidates (and then teams wonder why they’re nothing but white guys). I’ve never been happy working with someone who couldn’t do the job just because they shared my interests.

Liking a person and respecting a person are not the same thing (nor are they mutually exclusive) and while I don’t need to be BFF with all my coworkers I do need to respect them and be respected by them. __We should focus on finding coworkers we respect who can do the job, not finding a [Work BFF](https://en.wikipedia.org/wiki/Best_friends_forever). Culture fit questions don’t help.__
