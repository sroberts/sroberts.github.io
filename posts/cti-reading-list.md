---
title: CTI Reading List
date: 2017-07-18T05:00:00.000Z
tags:
  - intelligence
  - learning
---

![](https://cdn-images-1.medium.com/max/800/1*ut9WKlGu6brb5r1A_x4JOA.jpeg)

A few weeks ago while teaching [SANS FOR578](https://www.sans.org/course/cyber-threat-intelligence) one of my students asked a great question by a student: _What books or papers should a new cyber threat intelligence analyst read first?_ It’s a question I’d meant to answer before so instead of just sending back an email (I mean, I emailed back, _HI MATT_, but along with that) I figured I’d write up my list and have something to reference next time I get asked. So here’s my list of things you should read when getting started in cyber threat intelligence:

### Books

Get that library card or Amazon account ready, here are my favorite books on CTI.

### 📘 [The Cuckoo's Egg](https://www.goodreads.com/book/show/18154.The_Cuckoo_s_Egg)

The best narrative version of the DFIR & CTI world I can imagine The Cuckoo’s Egg reads better than Tom Clancy and tells the true story of an astronomers year hunting cyber espionage in the early 1980s. A must read (and great for non-technical folks as well). Also a great gauge of interest for people thinking about dipping their toe into DFIR or CTI.

### 📘 [Secrets and Lies](https://www.goodreads.com/book/show/304482.Secrets_and_Lies)

Written in 2000 Secrets and Lies was my introduction to many of the technical problems in security and has been my go to _First Technical Security Book_ ever since. I’m reevaluating it now (against the [Defensive Security Handbook: Best Practices for Securing Infrastructure by Lee Brotherston & Amanda Berlin](https://www.goodreads.com/book/show/31805609-defensive-security-handbook?from_search=true)) but Secrets and Lies is a classic.

### 📘 [Incident Response & Computer Forensics, Third Edition](https://www.goodreads.com/book/show/16691213-incident-response-computer-forensics-third-edition?from_search=true)

Ultimately CTI collection is the output of incident response. Doing CTI well requires a deep understanding of all aspects of Incident Response and Incident Response & Computer Forensics is the best book to learn the overall process from some folks who’ve been there and done that.

### 📘 [Practical Malware Analysis](https://www.goodreads.com/book/show/10677461-practical-malware-analysis)

A huge amount of CTI comes down to malware analysis. Malware reverse engineering is a big part of understanding the capabilities of an adversary. This is the best introduction text I know. In fact it’s on my current reread list.

### 📘 [Thwarting Enemies at Home and Abroad](https://www.goodreads.com/book/show/5979810-thwarting-enemies-at-home-and-abroad)

**SHOCKER:** _You’re not an intelligence analyst if you’re doing CTI. You’re a counter intelligence analyst._ Many of the same techniques, but a totally different application. Understanding traditional counterintelligence tradecraft is essential and this is my favorite book to learn it.

### 📘 [Structured Analytic Techniques For Intelligence Analysis](https://www.goodreads.com/book/show/7818985)

Analysis is often the least understood (and honestly least undertaken) piece of CTI. We, all of us in the CTI arena, need to get better at it. Richards Heuer literally wrote the book on this.

### 📘 [Dark Territory](https://www.goodreads.com/book/show/25814289-dark-territory)

Like The Cukoo’s Egg Fred Kaplan’s Dark Territory is a story centric a history of the development of America’s cyber warfare capability and provides a detailed look into what developing a cyber warfare capability looks like at a policy level.

### Papers

Plenty of key concepts don’t merit a full book but are more in the 10–30 page range which are perfect for academic style papers. These are good ones to start with:

- 📄 **[Threat Intelligence: Collecting, Analysing, Evaluating](https://www.mwrinfosecurity.com/assets/Whitepapers/Threat-Intelligence-Whitepaper.pdf)** — I read this paper right when it came out (though I had to be reminded of it by [John D. Swanson](https://medium.com/u/def0f8c74684)) and it’s a solid broad introduction to the core concepts of CTI. It’s not enough on it’s own, but it’s a solid start.
- 📄 **[Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains by Hutchins, Cloppert & Amin](https://www.lockheedmartin.com/content/dam/lockheed/data/corporate/documents/LM-White-Paper-Intel-Driven-Defense.pdf)** — The infamous kill chain paper. Love it or hate it this is a seminal work defining a model that every CTI analyst needs to understand even if they don’t use it directly.
- 📄 **[The Diamond Model of Intrusion Analysis by Caltagirone, Pendergast, & Betz](http://www.activeresponse.org/wp-content/uploads/2013/07/diamond.pdf)** — Another key model I admit I dismissed the Diamond model at first. Four simple buckets, how big a deal is that? Turns out it’s a huge one after I got past the TLDR. Not simple actually, but elegant.
- 📄 **[Psychology of Intelligence Analysis by Heuer](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis/PsychofIntelNew.pdf)** — Added by popular demand I had this paper on the list originally, but took it off since it’s basically a subset of Heuer’s Structured Analytic Techniques listed above. That said this is a seminal paper on the human aspect of analyzing intelligence, so I’m adding it back. _Thanks for the suggestions!_

#### **Adversaries**

Most CTI programs are focused on four major sets of adversaries: China, Russia, the United States, & everyone else (I’ll write another post about that bias later on). Who’s important will depend on your threat model including geographic location and industry, but passing familiarity with the big players is important for everyone. Here’s are my favorites introductions:

- **China:** 📄 [APT1 Report](https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf) & 📄 [Op SMN/Axiom Report](http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf) — One sorta basic, one more advanced. A good cross section of Chinese state sponsored espionage.
- **Russia:** 📄 [Peering Into the Aquarium](https://www.documentcloud.org/documents/3461560-Google-Aquarium-Clean.html) — A leaked Google report (everyone has leaks) but the best survey of Russian threat actors I know of.
- **United States:** 📄 [Equation Group](https://securelist.com/files/2015/02/Equation_group_questions_and_answers.pdf) — No one says US but it's very clear. A great idea of the sort of capabilities everyone else wants to have.
- **Everyone Else:** 📄 [Careto](https://kasperskycontenthub.com/wp-content/uploads/sites/43/vlpdfs/unveilingthemask_v1.0.pdf), 📄 [Ocean Lotus](https://www.fireeye.com/blog/threat-research/2017/05/cyber-espionage-apt32.html), 📄 [Desert Falcon](https://securelist.com/files/2015/02/The-Desert-Falcons-targeted-attacks.pdf), & 📄 [Dark Seoul ](https://www.mcafee.com/us/resources/white-papers/wp-dissecting-operation-troy.pdf)— A wide variety in three groups. Varied tactics & goals.

## Non-Computer Network Defense Specific Reading

While the books above are very technically focused on computer network defense (CND) but there are a wide variety of subjects useful to a CTI analyst that go beyond CND & intelligence. Here’s my starting list:

### 📘 [Near and Distant Neighbors](https://www.goodreads.com/book/show/22929502-near-and-distant-neighbors)

An exploration of the formation of the modern Russian intelligence apparatus. Studying those evolutions is interesting.

### 📘 [The Art of War](https://www.goodreads.com/book/show/10534.The_Art_of_War)

Judge if you want, it’s a solid read detailing the meta nature of conflict and espionage. Yes it’s overdone, yes it was over quoted, but it’s still valuable. Ignore it at your own peril. (Want a more modern take? I’ve been meaning to read [On War by Carl von Clausewitz](https://www.goodreads.com/book/show/117031.On_War).)

### 📘 [Thinking, Fast and Slow](https://www.goodreads.com/book/show/11468377-thinking-fast-and-slow)

So I haven’t read this one (yet)… but I’ve been meaning too. From podcasts and discussions with friends it’s a perfect for this list so I’ll add it, even if it is still aspirational to me. Very meta-cognitive.

### One Last Reading Idea

[Rebekah Brown](https://www.twitter.com/pdxbeks) and I have been working very hard and are excited to share our own addition to this list:

![Intelligence Driven Incident Response](https://cdn-images-1.medium.com/max/800/1*NLqyztM4ZkcrgL9gwdYDQQ.png)

[Intelligence Driven Incident Response](http://shop.oreilly.com/product/0636920043614.do)

Our book is meant to cover both the network defense process and the intelligence process but more importantly how they can be integrated. Ultimately computer networks defense takes intrusion detection, incident response, & intelligence.

### Bonus! 🎥 [Jiro Dreams of Sushi](http://www.imdb.com/title/tt1772925/) & 🎥 [Sour Grapes](http://www.imdb.com/title/tt5728684/)

As I was originally thinking about this post I thought it would be nothing but Intelligence & Incident Response books, but as I kept considering the topic it kept expanding and I wanted to be encompassing. So in addition to some reading here are two movies I watched and couldn’t stop thinking of parallels to CTI.

![](https://cdn-images-1.medium.com/max/800/1*67elwEWXeu65pS7GCOqnBA.png)

Photo from [The Gumroad](https://gumroad.com/l/jiro)

**[Jiro Dreams of Sushi](http://www.imdb.com/title/tt1772925/)** is a beautiful documentary about food, but more than that about the depth of effort and dedication it takes to really be the best at a craft. This is all the more important in an adversarial vocation like CTI, where in many cases it matters who’s better, you or the adversary. For me I would like to be known as having the kind of tenacity as Jiro and those who work with him.

![](https://cdn-images-1.medium.com/max/800/1*2_uu9-CiDo0HscwqtJiMLA.png)

Photo from [The Pool](https://www.the-pool.com/arts-culture/tv/2016/47/what-to-watch-tonight-23-11)

**[Sour Grapes](http://www.imdb.com/title/tt5728684/)** touches on a different but no less important, borderline unteachable, aspect of CTI/IR. I won’t spoil the surprise, but Sour Grapes is a wonderful lesson in the investigative desire, that need to track down the adversary and figure out their techniques and goals.

I recommend both highly and they’re both excellent to watch even with non-CND people. They also pair with tuna nigiri and an off-dry Riesling.
