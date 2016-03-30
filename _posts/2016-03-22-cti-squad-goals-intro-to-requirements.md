---
layout: post
title: CTI SquadGoals - Setting Requirements
---

![Squad Goals](https://ccwebcontent.blob.core.windows.net/resources/blobs/images/870x489/artwork-squadgoaldesccover.png)

I'll be honest... I didn't think to write this post until I'd been getting reviews about the next post. I started writing about planning intelligence collection and how organizations should approach it. A kind friend who's good enough to edit much of what I write asked where my requirements post was. He was right, I was putting the cart before the horse, the exact kind of thing I pontificate on not doing.

Here we are. Requirements. The first part of the intelligence cycle and the most neglected. According to the [appendix of Joint Publication 2-0: Joint Intelligence](http://www.dtic.mil/doctrine/new_pubs/jp2_0.pdf)

> <i class="fa fa-quote-left fa-3x pull-left"></i>__intelligence requirement.__ 1. Any subject, general or specific, upon which there is a need
for the collection of information, or the production of intelligence. 2. A requirement for
intelligence to fill a gap in the command’s knowledge or understanding of the
operational environment or threat forces.

Requirements set the entire priority of your intelligence cycle, what sources you collect from, what types of processing you need to do, and what methods of dissemination will meet the need. Where your team is focusing, aka Squad Goals. Lets get started...

## Business Plan Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i>If there are two men, Rod and Rob, and you can only steal from one, which one would you choose? The answer is: Whichever one is a banker. ~ _Jarod Kintz_

The first place I start thinking about collection is realizing your own business plan and what that entails. Certain actors target resources in a way that you can rule them in scope or out of scope:

- Are you a bank or financial institution? Financially motivated attackers are interested in you and intellectual propriety focused attackers aren't. Same thing with _big institution attackers_ like Anonymous.
- Are you doing energy exploration? The Black Energy Team might be targeting you.
- Do you invent pharmaceuticals? Look for actors that try to steal information like that.

CrowdStrike actually illustrated this in their "Uncover the Adversary" map:

![Crowdstrike Actor Map](public/crowdstrike-map.png)

So using this as an example:

- If you're an oil company you should be on the look out for Cutting Kitten, Energetic Bear, & Ghost Jackal.
- What about finance? Focus on Deep Panda, Impersonating Panda, & Singing Spider.
- Governments may want to focus on Anchor Panda, Silent Chollima, & Viceroy Tiger.

Will these always be perfect? Certainly not, but they provide a solid starting point. Your industry heavily defines your threat model and thus should define your intelligence requirements.

## Geographic Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> I get to go to overseas places, like Canada. ~ _Britney Spears_

Geography is a tricky thing. The Internet lets us be across the world in a second, at the same time it's often an extension of real life. Attackers take advantage of geographic distribution to remain semi anonymous, but in others they use computer network attack to project a different kind of power within the region.

![ZOMG MAP OF HACKER STUFF](public/uplink-server-map.jpg)

The [Naikon Group](https://www.threatconnect.com/camerashy/) is a good example. Public reports say they're focused on operations within South East Asia such as Nepal, the Philippines, Thailand, etc. Don't live in South East Asia? For the most part Naikon is probably not super interesting to you. Living in Singapore? You should probably be paying attention. This is true for many organizations, including dissident groups. Even though Naikon could easily strike across the world (and may do so) it would be sloppy to not consider location in defining intelligence requirements.

_**Aside:** That said there are few greater lies than thinking you know where someone is in the world with computers. VPNs are easy and hotpoints can be anywhere. Avoid assuming too much when it comes to the Internet and physical location._

## Technology Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> Windows 2000: Designed for the Internet. The Internet: Designed for UNIX. ~ _Unknown_

![](http://media2.giphy.com/media/M3o3fL9nnxG4o/giphy.gif) It's common to think of most actors as omnipotent though they are not. They have limits, budgets, time, etc. As a result most attackers are familiar with attacking certain kinds of infrastructure and systems. A Windows network running Active Directory is in some ways harder to attack than a Linux network on LDAP (don't knock MSFT, they've invested a lot in security over the last 15 years) but the fact is most attackers are probably more familiar and invested in attacking Windows & AD than Ubuntu and OpenLDAP.

When developing intelligence requirements take the time to look around your infrastructure, what makes you special? Do you run lots of Industrial Control Systems? You should probably be paying attention to different attackers than a law firm running all Macs. Part of this is vulnerability management as well, understanding the flaws that are out there for the systems you protect.

## Vertical Requirements

> <i class="fa fa-quote-left fa-3x pull-left"></i> I would rather walk with a friend in the dark, than alone in the light. ~ _Helen Keller_

One of the least appreciated approaches to forming intelligence requirements is asking others. It almost seems too simple. If you're a university in a particular part of the world then being in touch with other universities near by makes sense, and learning from the incidents they've had and the attacks they've faced is potentially a help. Industry has been espousing this for years with the formation of Information Sharing and Analysis Centers such as [FS-ISAC](https://www.fsisac.com/), [the Retail Cyber Intelligence Sharing Center](https://r-cisc.org/), and others. Whether formal or informal these groups provide the chance to learn from others and avoid making the same mistakes twice.

## One Offs

> <i class="fa fa-quote-left fa-3x pull-left"></i>Reports that say that something hasn't happened are always interesting to me, because as we know, there are known knowns; there are things we know we know. We also know there are known unknowns; that is to say we know there are some things we do not know. But there are also unknown unknowns – the ones we don't know we don't know. And if one looks throughout the history of our country and other free countries, it is the latter category that tend to be the difficult ones. ~ [_Donald Rumsfeld_](https://en.wikipedia.org/wiki/There_are_known_knowns)

And then there are the odd bits. They may come in when a higher up is watching CNN in the airport or they may come from a spooky government source. No matter what they will show up at some point and become part of your intelligence requirements, maybe as a one time addition, maybe on an ongoing basis. Don't discount them.

## Writing Strong Requirements

The best intelligence requirements are specific enough to direct answering the question. Here are some characteristics that lead to good intelligence requirements:

- __Singular:__ A strong requirement focuses on one question and only one question.
- __Atomic:__ The requirement should be specific to a particular fact or event.
- __Decision Centric:__ The requirement should lead to making a decision.

It takes time and practice to develop good requirements.

| Weak Requirement | Strong Requirement |
| ---------------- | ------------------ |
| What actors might attack our company? | Is X actor still active? |
| What indicators should we be using in our IDS? | What are current file system indicators of Actor X? |
| Are there actors targeting the location we're in? | Is an actor specifically targeting Region Y? |
| What malware should we look for on our network? | Is Locky being used to attack companies like mine? |

Practice makes perfect, but working with others to sharpen your requirements writing is even better.

## Just the Start

Even though they're commonly missed the fact is developing good requirements sets the solid foundation for a good intelligence cycle. If you want to read more the CIAs Center for Intelligence Studies has a great article [A Fresh Look at Collection Requirements](https://www.cia.gov/library/center-for-the-study-of-intelligence/kent-csi/vol4no4/html/v04i4a03p_0001.htm) and
Army Field Manual 34-2 Collection Management to Support Commanders includes the appendix [Developing Priority Intelligence Requirements](http://fas.org/irp/doddir/army/fm34-2/Appd.htm). Read those and you'll be on the right track.
