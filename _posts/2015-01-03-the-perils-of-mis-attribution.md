---
layout: post
title: The Perils of Attribution
---

It's impossible to be involved in the information security community right now and to avoid [the issues going on at Sony](http://www.wired.com/2014/12/sony-hack-what-we-know/). The details of the attack by "The Guardians of Peace" may never be fully known, but it is safe to say that this has become one of _the_ defining computer security events from a public perspective. Plenty of people are addressing this from a variety of angles so I just want to speak to one, some what tertiary but none the less key issue, the "attribution" debate.

## A bit of History

In every major security incident one of the first questions asked is "Who"? We call this attribution (we'll go into detail on that word later). Defining this boogie man has been the major driver of information security hype cycles since the beginning of our profession.

| Timeframe | Event | Boogie Man | Result |
| ------ | ----- | ---------- | ------ |
| 1980-1990s | The Great Hacker War & [multiple government intrusions](https://en.wikipedia.org/wiki/Moonlight_Maze). | Basement Hackers ([LOD](https://en.wikipedia.org/wiki/Legion_of_Doom_(hacking)), [CDC](https://en.wikipedia.org/wiki/Cult_of_the_Dead_Cow)) &  Nation State Hackers. | Selling lots of firewalls.  Inventing IDS. [Wargames!](http://www.imdb.com/title/tt0086567/) |
| Mid 1990 - Mid 2000s | Endless computer worms: [Code Red](https://en.wikipedia.org/wiki/Code_Red_(computer_worm)), [Slammer](https://en.wikipedia.org/wiki/SQL_Slammer), etc | Criminals & Pranksters | The AntiVirus Market. Ended largely with [Conficker](https://en.wikipedia.org/wiki/Conficker). |
| Dec 31 1999 | [Y2K Bug](http://content.time.com/time/specials/packages/article/0,28804,2072678_2072683_2072599,00.html) | Unknown bugs and unintended consequences | Nothing. Zip. Zilch. Nada. Society continues. |
| ~2009 - 2012 | China Peoples Liberation Army (APT) | [Google got hacked](http://googleblog.blogspot.com/2010/01/new-approach-to-china.html), suddenly everything was China/APT. [Mandiant released the APT1 report](https://www.mandiant.com/blog/mandiant-exposes-apt1-chinas-cyber-espionage-units-releases-3000-indicators/). Everyone at the RSA Conference promised "Anti-APT" solutions. |
| 2012 | Dozens of high profile activist hacks | Anonymous & LulzSec | Cyber hactivism is touted as the next great threat to the world. It's been mostly ignored and a few Twitter accounts were compromised. |
| Summer 2013 | [The Snowden Leaks](https://en.wikipedia.org/wiki/Global_surveillance_disclosures_(2013–present)) | [NSA TAO/ANT](https://en.wikipedia.org/wiki/Tailored_Access_Operations) | Global mistrust of the US intelligence community. The "Anti-NSA"-ifying of various domestic American companies and a slight global move away from American tech companies. |
| November 2014 | North Korea | Sony gets hacked by a group claimin to be called the "Guardians of Peace". The press leaks speculation it's actually North Korea. Suddenly everything is North Korea information warfare. Vendors release their DPRK reports. The FBI confirms the press rumors. President Obama announces sanctions. |

The first thing that needs to be noted is none of these time frames are accurate. Every one of these groups & threats have been active before & since their "time in the sun". What these rough dates frame is the hype cycle; when the media and vendors have emphasized these various issues. This represents a moving idea of "who the bad guy is" that's largely based on a single idea: __attribution__.

## Definitions

Attribution is a loaded word, even in the simplest terms. According to my handy Dictionary.app:

> attribute: verb \|əˈtriˌbyo͞ot\| [ with obj. ] (attribute something to)
>
> - regard something as being caused by (someone or something): he attributed the firm's success to the efforts of the managing director \| the bombing was attributed to the IRA.
- ascribe a work or remark to (a particular author, artist, or speaker): the building was attributed to Frank Lloyd Wright.
- regard a quality or feature as characteristic of or possessed by (someone or something): ancient peoples attributed magic properties to certain stones.

In short attribution is two different things:

- tying an action to a specific actor
- characterizing a certain aspect of an action

Reading these definitions attribution seems like a wildly reasonable thing in the event of a security incident. So why the fuss?

## Short Answer
_Attribution is Hard_.

## Long Answer

Accurate attribution of attacks is difficult under the best of circmstances and there are a few key, common issues.

### Incomplete Information
In most cases collecting data on security events is difficult. Very few organizations really have sufficient, comprehensive monitoring (full network content monitoring, endpoint monitoring, centralize logging, etc) necessary to recreate any and every event after the fact. Recreating incident are difficult even if you can acquire the malware and exploit vector (phishing email or watering hole). So at best most security teams are working with incomplete information.

### Circumstantial Information
At it's core one of the most attractive things about offensive network operations is [how easy it is to be someone you're not](http://en.wikipedia.org/wiki/On_the_Internet,_nobody_knows_you're_a_dog).

![On the Internet no one knows you're a dog](http://upload.wikimedia.org/wikipedia/en/f/f8/Internet_dog.jpg)

- IP Addresses are easy to fake with VPN software or a cheap VPS, thus seeming to come from any country you like.
- Most of the Internet doesn't require any real form of ID, it's simple to sign-up for Facebook, Twitter, or SSL certificates as anyone.
- Anonymous payments are easier than most people realize. That means VPS, VPN endpoints, etc.

In a world where many characteristics are easily changed, manipulated, or mimicked it's no wonder attribution is difficult.

## Operational Security

During any security incident [operational security](http://www.dodea.edu/Offices/Safety/upload/01_Brief_Basic_OPSEC.pdf) is paramount. This takes on 3 aspects:

- Internal: You don't want your own employees taking actions that undermine your investigation or recovery. This is actually a fairly common issue.
- External: Letting information leak about your investigation can cause dangerous speculation among outside forces, most notably the press. This can affect a companies financial standing well beyond the scope of an incident. Damage control such as this may not be important to an incident response team, but it's critical to stock holders and the C-Suite.
- Attacker: The most important operational security concern is preventing any information from getting back to your attacker. If an attacker believes you're on to them they could take a number of actions: destroy data, change their malware or infrastructure, steal data at a quicker pace, or disappear entirely. Any one of these can be devastating.

As a result its key that information that could lead to those outcomes is carefully controlled and only released when it can't cause any damage.

## So What about Sony

I cannot say for certain, having had nothing to do with the investigation, but I would speculate that in this case all 3 (incomplete information, circumstantial information, and operational security) all play a role.

### Incomplete Information

I don't want to kick someone when they're down, but [there's been plenty of information to suggest Sony's security team wasn't operating at 100%](http://time.com/3620288/sony-hack-unprepared/). It seems reasonable to believe they may not have been in a position to identify and gather information about the attack when it happened. This would lead to gaps of information that would be difficult to reconstruct.

### Circumstantial Information

This part is the same in every investigation. It is easy to bite and attempt to use information like IP geolocation or certificate data or language pack information, treat it as fact, and make assumptions about an attacker. That isn't to say this information is useless, contrary it's highly valuable data, but it does have to be used carefully. Data itself needs to be [developed before it can be considered intelligence](http://www.fbi.gov/about-us/intelligence/intelligence-cycle).

"Carefully" in events like this is tough. It's hard for security teams, it's all but impossible for the press or firms trying to feed off the marketing potential of a new and exciting boogie man. Circumstantial evidence like this, coupled with confirmation bias, can often lead to jumping to obvious, even _convenient_, conclusions.

### Operational Security

Plenty of people have questioned the FBI's attribution to North Korea. One of the things most commonly cited is how little information they provide, much of which was circumstantial. This concern neglects, or at least naively ignores, what information they're [withholding deliberately](http://www.thedailybeast.com/articles/2015/01/02/u-s-spies-say-they-tracked-sony-hackers-for-years.html).

Does the FBI/US Gov have better sources than they're letting on? I would guess yes. But burning good sources just to make naysayers feel better isn't good intelligence management.

#### Damage Control

A lot has been made of [Kevin Mandia's comments about the sophistication of the Sony attack](http://recode.net/2014/12/07/sony-describes-hack-attack-as-unprecedented/). Some people have suggested that this leader of one of the best investigation teams saying what he said means this really was an advanced and sophisticated attack. Some have suggested this was just him providing some cover for Sony leadership.

It's difficult to say which is more the case, though personally I lean towards the former. Regardless this is one of the services an experienced IR firm provides: assuring the public that the situation is being handled by professionals and easing concern. The Mandiant team, being that they're actually involved in the incident and an experienced team, has a far better perspective than I do.

## Good Attribution

So lest I just seem negative lets talk about what makes good, effective attribution:

- Comprehensive telemetry collected from multiple sources
  - Network full content is great, flow & proxy logs are great too.
  - Memory and system logs from any systems the bad guys get into are key.  
- Extensive Analysis by multiple experts (hopefully corrobrated by multiple analysts)
  - Compromised system memory analysis
  - Compromised system disk forensics
  - Deep malware analysis (dynamic and static, as well as utilizing a comprenshive malware library)
  - Log correlation, especially centralized authentication lots
  - Open source analysis of the attackers infrastructure (attack infrastructure, C2 & exfiltration nodes)
- Analyzed Multiple Attacks against a single Victim
  - It's incredibly difficult to see one incident, even a long running one, and develop meaningful attribution.
  - Many attackers will come back to the same victim multiple times. Comparing these multiple attacks can give incredible insight into how the attacker evolves, what resources they keep going after, etc.
- Multiple sets of telemetry from one incident
  - In many cases attackers use the same tool chain & tactics, techniques, and proceedures against multiple victims.
  - By sharing information between similar organizations who see the same attackers you get yet another oppertunity to

At it's core there are two ultimate goals conducting this analysis:
- Identify common tactics, techniques, and proceedures
- Identify common attacker goals (actions over target)

This process is not for the faint of heart. It takes time, good information, and a skilled team to turn the necessary mountain of data into verifiable, trustworth attribution. Even if a team can accomplish that making the case can be difficult. Plenty of people in the security world are happy to be contrarian for a variety of motivations.

### Actor vs Attribution

When conducting this analysis the question is "what's the goal?". Being able to put a name to an actor is psychologically incredibly useful, but does that mean it's necessary to have a persons given name or the name of their employer for this to be a worthwhile exerise? In my experiece this makes for great marketing fodder, but unless you have hand cuffs (and necessary legal documents to use them) or cruise missiles (and war powers) what good is "direct attribution"? I'd argue none at all.

Being able to tie a series of TTPs to a name, even just a made up code name, is highly valuable and removes the "boogie man" fear that most people have to attackers over the Internet. Teams that take this "indirect attribution" approach will start to recognize these code named actors. This leads to faster identification, more effective remediation, and eventually the ability to start applying counter intelligence approaches. This should be every incident response teams ultimate goal.

## Conclusion

So what's my take: Are the Guardians of Peace actually North Korea? This may be the the unpopular response, but I'll say it anyway: _I don't know_. I haven't analyzed the malware, studied the packet captures, seen the phishing emails, or anything else relative to the investigation. I know there are smart people working this incident and I trust they're taking every step necessary.

What I do know is that we are making major decisions based on the idea that this attack can be attributed to the Democratic Peoples Republic of Korea. I don't just mean whether companies buy a new tool from a vendor with a good graphics department, I mean [major international policies](http://www.foxnews.com/politics/2015/01/02/obama-administration-imposes-sanctions-on-north-korea-after-sony-hack/). I urge anyone, from federal law enforcement & policy makers to lowly incident responders like myself: be careful pointing & un-pointing fingers. Attribution is difficult when you're in the middle of an investigation, and all but impossible to an armchair quarterback.  