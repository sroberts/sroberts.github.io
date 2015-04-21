---
layout: post
title: Incident Response Hunting Tools
---

Great, you've [decided to move beyond reactive incident response and start hunting](/2015/04/14/ir-is-dead-long-live-ir/). While hunting is primarily a way of thinking about incident response it does rely on your technical capabilities, so what tools should you use? The focus for me is always on open source tools with tools with wide ranging applications. Here are my favorites:

### Endpoint Alerting Tools: [Facebook osquery](https://osquery.io/)

![Facebook osquery Screenshot](http://ycom.cat/wp-content/uploads/2014/10/portada_osquery.jpg)

osquery is a tool from Facebook that describes itself as:

> osquery allows you to easily ask questions about your Linux and OSX infrastructure. Whether your goal is intrusion detection, infrastructure reliability, or compliance, osquery gives you the ability to empower and inform a broad set of organizations within your company.

If I'm honest I wasn't crazy about osquery at first (Sorry Mike). The SQL syntax, while familiar, felt forced and awkward to me. That said I've looked high and low and have yet to find a better endpoint alerting tool than osquery. It's fast, flexible, and fully featured. Tools like [Mozilla MIG](http://mig.mozilla.org/) are interesting and maturing quickly, but osquery is capable and ready to deploy, so I'll eat my works and osquery is my first pick. New tools like [Mephux's EnvDB](https://github.com/mephux/envdb) are just making it even better.

### Endpoint Interrogation Tools: [Google GRR](https://github.com/google/grr)

![Google GRR Screenshot](http://wiki.grr.googlecode.com/git/Screenshot%20from%202013-11-18%2018:36:46.png)

Google Rapid Response (GRR) was built by Google in the wake of their [Aurora Incident](http://www.wired.com/2010/01/operation-aurora/) to do incident response at scale across a wide variety of operating systems and geographies. Billed as:

> GRR Rapid Response is an incident response framework focused on remote live forensics.

GRR makes it possible to directly interrogate individual systems or _hunt_ across a wide swath of systems. Able to pull memory, search for file system artifacts, audit user activity, search network usage, GRR provides a comprehensive experience for investigating malicious activity. The server can be stood up with one script and then just start deploying the packaged agents to start hunting.

### Comprehensive Logging: [Elasticsearch](https://www.elastic.co/products/elasticsearch), [Logstash](http://logstash.net/), & [Kibana](https://www.elastic.co/products/kibana)

![Elastic ELK Screenshot](https://www.elastic.co/assets/blt45376e159402a169/Screen-Shot-2014-12-15-at-12.28.30-PM.png)

Three tools in one ELK combines a datastore (Elasticsearch), log ingestion pipeline (Logstash), and an analysis interface (Kibana) aka ELK. [Combined](https://www.youtube.com/watch?v=1uS5b8aQ6z8) they form a powerful log management and analysis platform, scalable to tremendous amounts of ingestion and retention.

For a hunt team this provides a singular location to store logs from all relevant systems, whether they be application logs such as your VPN or email server logs, network & system logs like [Bro](https://www.bro.org/) (Read @jshlbrd's [great post on using Bro for Hunting](http://jshlbrd.blogspot.com/2015/04/bro-whats-it-good-for.html)) or [auditd](http://linux.die.net/man/8/auditd), and provide a unified place to analyze them. This enables the kind of telemetry that makes a singular indicator valuable across a myriad of systems.

### Wide Ranging Network Visibility: [AOL Moloch](https://github.com/aol/moloch)

![AOL Moloch Screenshot](https://camo.githubusercontent.com/b129332e6f94c606e4b04d79d6d43f937b38e276/68747470733a2f2f7261772e6769746875622e636f6d2f77696b692f616f6c2f6d6f6c6f63682f73657373696f6e732e706e67)

As far as network visibility goes the ideal world is full content monitoring. Before Moloch there were limited options.

- A homebuilt system based on [tcpdump](http://www.tcpdump.org/), where all you're paying for is storage, but with a clunky interface.
- An expensive commercial system, great interfaces, but wildly limited storage coming with a crazy price tag.

Full stop.

Then came Moloch:

> Moloch is an open source, large scale IPv4 packet capturing (PCAP), indexing and database system. A simple web interface is provided for PCAP browsing, searching, and exporting. [...] Moloch is not meant to replace IDS engines but instead work along side them to store and index all the network traffic in standard PCAP format, providing fast access.

Moloch is one of the best designed, truly enterprise worthy open source projects out there, and an amazing solution for doing full content monitoring. It's a challenging tool to deploy, and can be expensive depending on retention, but it's the most flexible and featureful. Alternatives like flow monitoring or intrusion detection systems are highly effective as well, but less flexible.

### Tracking: [Societe Generale CERT's FIR](https://github.com/certsocietegenerale/FIR/)

![Societe Generale FIR Screenshot](https://raw.githubusercontent.com/wiki/certsocietegenerale/FIR/screenshots/incident_details.png)

It's easy to get caught up in systems that improve telemetry, but what you do with the information collected is just as important. Tracking a hunt is a complicated thing, with lots of data, lots of people, and often an adaptive adversary. It's important to have a structured way to record varied types of data, not just facts but also observations, hunches, etc.

I haven't personally spent a lot of time with it (something I plan to remedy soon), but as someone who's used numerous commercial systems, endless wikis, even just plain notebooks and whiteboards, I think FIR looks like one of the best systems at any price, and the best open source option by far. For a less incident centric, more intelligence centric tool give [CRITs](https://github.com/crits/crits) a look as well.

## How it Fits Together

At it's core these tools enable the [F3EAD Cycle](/2015/03/24/f3ead/) that is the core of the hunt. Telemetry tools and their use makes up the operations phase (Find, Fix, & Finish) while the Tracking provide a datastore and structure for the intelligence phase (Exploit, Analyze, & Disseminate). These tools make it possible to establish the F3EAD cycle. As you improve the efficency of this interplay you shorten your OODA cycle

## Conclusion

> <i class="fa fa-comments-o fa-2x pull-left"></i> "It's the man, not the machine" <br>~ Chuck Yeager

As important as tools are General Yeager is certainly correct in this case. Tools enable a team to hunt, but ultimately hunting is a team perspective, an attitude, more than a series of tools. Focus on building people, processes, and then focus on technology.
