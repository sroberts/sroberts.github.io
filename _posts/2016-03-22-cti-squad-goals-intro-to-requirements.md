---
layout: post
title: CTI SquadGoals - Setting Requirements
---

![Squad Goals](/public/squadgoals.png)

Requirements. The first part of the intelligence cycle and the most neglected. According to the [appendix of Joint Publication 2-0: Joint Intelligence](http://www.dtic.mil/doctrine/new_pubs/jp2_0.pdf)

> <i class="fa fa-quote-left fa-3x pull-left"></i>__intelligence requirement.__ 1. Any subject, general or specific, upon which there is a need
for the collection of information, or the production of intelligence. 2. A requirement for
intelligence to fill a gap in the command’s knowledge or understanding of the
operational environment or threat forces.

Requirements set the entire priority of your intelligence cycle, what sources you collect from, what types of processing you need to do, and what methods of dissemination will meet the need. Where your team is focusing, aka [Squad Goals](http://www.urbandictionary.com/define.php?term=Squad+Goal). Lets get started...

## <i class="fa fa-bullseye"></i> Past Incident Based Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> Effective leadership is putting first things first. ~ _Stephen Covey_

I've said it a thousands times, but place #1 to start is your own incident management system. Build requirements based on incidents you've already investigated, get to know every inch of them, inside and out. Why do you think firms with consultants who do incident response always have good intelligence? It's no coincidence, they set intelligence requirements based on the incidents they respond to and so should you. This isn't ground breaking, so we'll move on.

## <i class="fa fa-file-text"></i> Business Plan Based Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> If there are two men, Rod and Rob, and you can only steal from one, which one would you choose? The answer is: Whichever one is a banker. ~ _Jarod Kintz_

The first place to start thinking about collection is digging into your own business plan and what that entails. Certain actors target resources in a way that you can rule them in or out of scope:

- Are you a bank or financial institution? Financially motivated attackers probably want to attack you.
- Are you doing energy exploration? A handful of attackers specialize in that.
- Do you invent pharmaceuticals? Look for actors that try to steal intellectual property.

[CrowdStrike](http://www.crowdstrike.com/) illustrated this in their _Uncover the Adversary_ map:

![Crowdstrike Actor Map](/public/crowdstrike-map.png)

So using this as an example (and CrowdStrike vernacular):

- What about that bank? They'll want to focus on Deep Panda, Impersonating Panda, & Singing Spider.
- If you're an oil company you should be on the look out for Cutting Kitten, Energetic Bear, & Ghost Jackal.
- The firm with the new heart attack treatment? I'd be on the look out for Deep Panda, Union Spider, and Corsair Jackal.

These distinctions won't always be perfect but they provide a solid basis to develop requirements. Your industry heavily defines your threat model and thus is a rich starting point to begin defining your intelligence requirements.

## <i class="fa fa-globe"></i> Geographic Based Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> I get to go to overseas places, like Canada. ~ _Britney Spears_

Geography is a tricky thing. The Internet lets us access information across the world yet at the same time it's often an [extension of real life](http://www.pokemon.com/us/pokemon-video-games/pokemon-go/). Attackers take advantage of geographic distribution to remain semi-anonymous, but in others they use computer network attack to [project a different kind of power within a region](http://motherboard.vice.com/read/inside-the-unending-cyber-siege-of-hong-kong).

![ZOMG MAP OF HACKER STUFF](/public/uplink-server-map.jpg)

The [Naikon Group](https://www.threatconnect.com/camerashy/) is a good example. Public reports say they're focused on operations within South East Asia such as Nepal, the Philippines, Thailand, etc. Don't live in South East Asia? Naikon is probably not interested to you. Living in Singapore? You should probably be paying attention. This is true for a variety of organizations, including dissident groups. Even though an actor could strike across the world (and may do so) it would be sloppy to not consider location in defining intelligence requirements.

_**Aside:** Before you say it I agree, VPNs are easy and hotpoints can be anywhere. Avoid assuming too much when it comes to the Internet and physical location. And while you're at it lets get over the keyboard settings or language packs for attribution._

## <i class="fa fa-laptop"></i> Technology Based Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> Windows 2000: Designed for the Internet. The Internet: Designed for UNIX. ~ _Unknown_

It's a common mistake to think of attackers as omnipotent. They have limits, budgets, time, etc. As a result most attackers focus on attacking certain kinds of networks. A Windows network running Active Directory is often harder to attack than a Linux network on LDAP (don't knock MSFT, [they've invested a lot in security over the last 15 years](http://news.microsoft.com/stories/cybercrime/index.html)) but the fact is most attackers are probably more familiar and invested in attacking Windows & AD than Ubuntu and OpenLDAP.

![Nmap... because?](/public/nmap.jpg)

When developing intelligence requirements take the time to look around your infrastructure, what makes you special? Do you run lots of Industrial Control Systems? You should probably be paying attention to different attackers than a law firm running all Macs. Part of this is vulnerability management as well, understanding the flaws that are out there for the systems you protect.

## <i class="fa fa-users"></i> Vertical Based Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> I would rather walk with a friend in the dark, than alone in the light. ~ _Helen Keller_

One of the least appreciated approaches to forming intelligence requirements is asking others. Backs work with banks on similar criminal groups. A [university](http://www.wsj.com/articles/penn-states-engineering-school-computers-hacked-1431804110) could collaborate with [similar universities](http://www.thedailybeast.com/articles/2015/08/21/chinese-hackers-target-u-s-university-with-government-ties.html), and learning from the incidents they've faced can be a great help. Industry has been embracing this for years with the formation of Information Sharing and Analysis Centers such as [FS-ISAC](https://www.fsisac.com/), [the Retail Cyber Intelligence Sharing Center](https://r-cisc.org/), and others. Whether formal or informal these groups provide the chance to learn from others and avoid making the same mistakes twice.

## <i class="fa fa-check"></i> One Off Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> Reports that say that something hasn't happened are always interesting to me, because as we know, there are known knowns; there are things we know we know. We also know there are known unknowns; that is to say we know there are some things we do not know. But there are also unknown unknowns – the ones we don't know we don't know. And if one looks throughout the history of our country and other free countries, it is the latter category that tend to be the difficult ones. ~ [_Donald Rumsfeld_](https://en.wikipedia.org/wiki/There_are_known_knowns)

Then there are the odd bits. They may come in when a higher up is watching CNN in the airport or they may come from a spooky government source. No matter what they will show up at some point and become part of your intelligence requirements, maybe as a one time addition, maybe on an ongoing basis. Don't discount them.

##<i class="fa fa-pencil-square-o"></i> Writing Strong Requirements

The best intelligence requirements are specific enough to direct answering the question. Here are some characteristics that lead to good intelligence requirements:

- __Singular:__ A strong requirement focuses on one question and only one question.
- __Atomic:__ The requirement should be specific to a particular fact or event.
- __Decision Centric:__ The requirement should lead to making a decision.

It takes time and practice to develop good requirements.

| <i class="fa fa-minus-square"></i> Weak Requirement | <i class="fa fa-plus-square"></i> Strong Requirement |
| ---------------- | ------------------ |
| What actors might attack our company? | Is X Actor active? |
| What indicators should we be using in our IDS? | What are current file system indicators of Actor X? |
| Are there actors targeting the location we're in? | Is an actor specifically targeting Region Y? |
| What malware should we look for on our network? | Are attacker using [Locky](https://blogs.technet.microsoft.com/mmpc/2016/02/24/locky-malware-lucky-to-avoid-it/) my vertical? |

Practice makes perfect, but working with others to sharpen your requirements writing is even better.

## Just the Start

Even though they're commonly missed the fact is developing good requirements sets the solid foundation for a good intelligence cycle. If you want to read more the CIAs Center for Intelligence Studies has a great article [A Fresh Look at Collection Requirements](https://www.cia.gov/library/center-for-the-study-of-intelligence/kent-csi/vol4no4/html/v04i4a03p_0001.htm) and
Army Field Manual 34-2 Collection Management to Support Commanders includes the appendix [Developing Priority Intelligence Requirements](http://fas.org/irp/doddir/army/fm34-2/Appd.htm). Read those and you'll be on the right track.
