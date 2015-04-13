---
layout: post
title: Incident Response Hunting Tools
---

## Hunting Tools

Great, you've decided to move beyond reactive incident response and start hunting. ready to get started, now what tools should you use. The focus for me is always on open source tools with tools with wide ranging applications. Here are my favorites:

### Endpoint Alerting Tools: [Facebook OSQuery](https://osquery.io/)

![Facebook OSQuery Screenshot](http://ycom.cat/wp-content/uploads/2014/10/portada_osquery.jpg)

OSQuery is a tool from Facebook that describes itself as:

> osquery allows you to easily ask questions about your Linux and OSX infrastructure. Whether your goal is intrusion detection, infrastructure reliability, or compliance, osquery gives you the ability to empower and inform a broad set of organizations within your company.

If I'm honest I wasn't crazy about OSQuery at first (Sorry Mike). The SQL syntax, while familiar, felt forced and awkward to me. That said I've looked high and low and have yet to find a better endpoint alerting tool than OSQuery. It's fast, flexible, and fully featured. Tools like Mozilla MIG are interesting, but OSQuery is capable and ready to deploy, so it has to be my first pick. New tools like [Mephux's EnvDB](https://github.com/mephux/envdb) are just making it even better.

### Endpoint Interrogation Tools: Google GRR

![Google GRR Screenshot](http://wiki.grr.googlecode.com/git/Screenshot%20from%202013-11-18%2018:36:46.png)

### Comprehensive Logging: [Elasticsearch](https://www.elastic.co/products/elasticsearch), [Logstash](http://logstash.net/), & [Kibana](https://www.elastic.co/products/kibana) aka ELK

![Elastic ELK Screenshot](https://www.elastic.co/assets/blt45376e159402a169/Screen-Shot-2014-12-15-at-12.28.30-PM.png)

Three tools in one ELK combines a datastore (Elasticsearch), log ingestion pipeline (Logstash), and an analysis interface (Kibana). [Combined](https://www.youtube.com/watch?v=1uS5b8aQ6z8) they form a powerful log management and analysis platform, scalable to tremendous amounts of ingestion and retention.

For a hunt team this provides a singular location to store logs from all relevent systems, whether they be application logs, network & system logs, and provide a unified place to analyze them. This enables the kind of telemetry that makes a singla indicator valuable across a myriad of systems.

### Wide Ranging Network Visibility: [AOL Moloch](https://github.com/aol/moloch)

![AOL Moloch Screenshot](https://camo.githubusercontent.com/b129332e6f94c606e4b04d79d6d43f937b38e276/68747470733a2f2f7261772e6769746875622e636f6d2f77696b692f616f6c2f6d6f6c6f63682f73657373696f6e732e706e67)

### Tracking: [CERT Societe Generale's FIR](https://github.com/certsocietegenerale/FIR/)

![Societe Generale FIR Screenshot](https://raw.githubusercontent.com/wiki/certsocietegenerale/FIR/screenshots/incident_details.png)

## Conclusion

> <i class="fa fa-comments-o fa-2x pull-left"></i> "It's the man, not the machine" <br>~ Chuck Yeager

As important as tools are General Yeager is certainly correct in this case. Tools enable a team to hunt, but ultimately hunting is a team perspective, an attitude, more than a series of tools. Focus on building people, processes, and then focus on technology.
