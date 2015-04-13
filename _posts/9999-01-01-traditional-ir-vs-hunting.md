---
layout: post
title: Incident Response is Dead...<br>Long Live Incident Response
---

Talk to anyone in the _DFIR Illuminati_ and one of the topics that always comes up is _Hunting_. Much like threat intelligence & string theory people talk a lot about this, but nearly no one knows what it actually means.

![Get it? Hunting?](./public/hunting.png)

## Proactive vs. Reactive

At it's core _Hunting_ is about taking a proactive vs a reactive approach to identifying incidents.

- In _Reactive_ organizations an incident starts when notification comes in; whether that's an IDS or AV alert, or worse a phone call from the FBI or getting [Krebs](http://krebsonsecurity.com/)-ed. At that point an IR begins, reacting to the incoming event.
- In _Hunting_ organizations the IR team actively goes looking for incidents based on known patterns of activity, intelligence, even just hunches. Once the hunt team finds a new incident they begin an IR as usual.

## Building a Hunting Capability

What does it take to build a hunting team? A change in technology, mindset, and procedures.

###  Incident Response

The Hunting vs Non-Hunting process is singularly relevant to the Preparation & Detection phases (See the [SANS Incident Response Process](http://sroberts.github.io/2015/03/18/sans-ir/)) of an incident. Good hunting is useless unless your team can execute on the mitigation, remediation, and recovery phases effectively. Without that all you have is a larger incident load you'll be unable to respond to effectively. Before focusing on hunting make sure you have the processes in place to respond efficiently. Once your team has effective responses prepared you'll ready to start hunting.

### Wide Ranging Telemetry

A good hunt team can use a basic indicator, like an IPv4 address, in diverse ways while hunting. The more options a team has for getting telemetry the better their chances of identifying and corroborating malicious actions. Successful hunt teams have myriad technologies available to identify different types of activity in different ways.

An IPv4 address is useful for searching:

- _Application Logs:_ Like your VPN, Email Server, or custom internal apps that attackers may target or co-opt.
- _Network Flow:_ Traffic analysis being ideal for long running historical investigation.
- _Endpoint Logs:_ Getting data directly to clients makes correlating internal activity possible, such as lateral movement. It's also valuable when systems like laptops may exist outside your network primeter.

Having diverse vantage points provides redundancy as well as the option to use the best tool for the job.

### Scalability & Automation

The tough thing about hunting is you're trying to prove a true negative. Put more plainly: you're trying to prove their isn't something bad. What makes this tough _is the fact that it's impossible to prove a true negative._ You can never ultimately be sure you aren't digging deep enough.

The way to counter this is by hunting efficiently and widely. That requires a combination of scalability and automation. The ability to deploy, run, and collect all forms of telemetry should be centrally and programmatically managed. While hunting you never know whether you'll be scanning a small team worth of systems, or and entire division. Considering looking at the advances the _[devops](http://theagileadmin.com/what-is-devops/)_ movement has made for the operations world. Similarly a great hunt team needs function at scale.

### A Target Centric Mindset

> <i class="fa fa-comments-o fa-3x pull-left"></i> "Know thyself..."<br>~ Ancient Greek Proverb

The first question people ask when building a hunting capability is where to start (If you read about [F3EAD](http://sroberts.github.io/2015/03/24/f3ead/) this is the Find section), otherwise known as targeting. The first approach to take is "target centric."

The hunt team starts by evaluating internal projects and resources to determine valuable projects and resources and begins hunting assuming attackers want to compromise those valuable resources. If the hunt team knows Project Unicorn is valuable and possibly targeted, start hunting around people & systems involved with Project Unicorn. The challenge of target centric hunting is understanding the organization as a whole well enough to recognize important resources. Collaborating with higher level leadership can often make this process easier.

### An Actor Centric Mindset

> <i class="fa fa-comments-o fa-3x pull-left"></i> "The way I wrestle five-year-olds makes me think if I were ever attacked by a pack of midgets, I’d be OK. " <br> ~Jarod Kintz

In the age of named attack groups and big nation state attack exposés much of the focus is on actor centric hunting. Rather than focusing on the potential targets actor centric hunting requires the hunt team to develop intelligence about potential attackers, either from their own research or 3rd party sources, and seek to identify specific actors. This is a powerful approach, but first requires an understanding of the attacks you face. While threat intelligence firms may track dozens of different actors at best a fraction will be relevant to your organization. By building dossiers based on target driven hunts you develop the necessary understanding to mature into actor driven hunting.

### Management Buy In

Ok... #REALTALK: You would think that your leadership would want to know about all these newly discovered incidents and have the IR team remediate them. Turns out they often aren't, worse if you work in a regulated industry (like finance, medicine, or the DIB). Often leadership would rather [_keep their head in the sand_](http://www.weedist.com/wp-content/uploads/2012/06/Head-In-Sand.jpg) than deal with the reality (like regulators & reporting requirements), and the hunt team becomes a victim of it's own success. I know of one organization where management told a mature hunting team to [watch movies](http://www.imdb.com/title/tt1190536/) and [play video games](http://www.hedgewars.org/) rather than track down more malicious activity. #truestory

### Operational Tempo

The incident response team being a _victim of their own success_ aren't limited to leadership. Once a hunt team begins to mature their ability to constantly find new malicious activity continues to improve until the point where they can basically find new malicious activity at will. As a result the IR team is basically in a constant state of emergency, always responding to something.

At this point the hunt team lead needs to step in and develop an operational tempo to keep the team sane. While in reactive organizations treating every incident as an all hands on deck emergency makes sense this can't be the reality of a hunt team as the team might always be in a state of emergency. You may soon discover that throwing out an entrenched attacker on Friday may lead to a new phishing campaign on Monday, and every day can't be an emergency or the fatigue will overwhelm and undermine your entire program. Even during an incident, and there will always be one, vacations are important and day to day work needs to get done. Exceptions happen, but they're rare.

## So what's the big deal?

![A Borne Hunter!](./public/borne.png)

In some organizations hunting seems like a mythical concept, in others it seems like business as usual. Hunting is still just a mindset, an idea of focusing on proactive action, rather than reactive response. Done well this mindset can change your organizations entire posture. It's not comfortable, it's not easy, but it's the difference between being passive and taking action. In my next post I'll talk about some of the better open source tools for equipping an up and coming hunt team.
