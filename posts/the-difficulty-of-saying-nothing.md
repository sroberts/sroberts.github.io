+++
date = 2022-03-21T05:00:00Z
layout = "page"
tags = ["network-defense", "intelligence"]
title = "The Difficulty of Saying Nothing"

+++
Like everyone else I've been following the tragic war in Ukraine and mourning the loss of life and humanitarian crisis. Professionally as an analyst in the threat intelligence and computer network defense world I've been considering what this war and spillover means for defending networks, especially as organizations like [CISA keep putting out bulletins regarding threats of Russian nexus adversaries](https://www.cisa.gov/news/2022/03/15/mitigating-threats-posed-russian-state-sponsored-cyber-actors-exploitation-default 'MITIGATING THREATS POSED BY RUSSIAN STATE-SPONSORED CYBER ACTORS’ EXPLOITATION OF DEFAULT MULTIFACTOR AUTHENTICATION PROTOCOL AND "PRINTNIGHTMARE" VULNERABILITY').

In situations with this level of uncertainty it's entirely natural that our intelligence customers, whether that's the most junior SOC analyst or executive like the CISO, keep asking what it means, what we can do, where the threats are, etc. It's easy to provide answers when there are obvious events to point at, write new reports about active exploitation, submit new IOCs or signatures. What is challenging for us in a situation like this one, a situation I think many security teams paying attention to Ukraine and the related Russian nexus threat actors are in, is saying the opposite: Nothing.

![Scumbag Steve - Writes a topical intelligence report Major Finding: Nothing Significant to Report](https://memegenerator.net/img/instances/86163283.jpg)

## Nothing Significant to Report

Now _Nothing Significant to Report_ (NSTR) is nothing new for intelligence teams. It's in fact the most common situation to find oneself in. For the most part if you throw a dart at a board of specific threat groups or even nexus countries chances are the intelligence on the entity you hit would be the same: nothing significant to report.

This has been a problem for many security teams as the cyber side of the Russian war on Ukraine has been different than what many of us expected. Even Bruce Schneier called this out: [Where’s the Russia-Ukraine Cyberwar?](https://www.schneier.com/blog/archives/2022/03/wheres-the-russia-ukraine-cyberwar.html "Where’s the Russia-Ukraine Cyberwar?") While there have been reports of some [wiper activity targeting Ukrainian government systems](https://www.crowdstrike.com/blog/technical-analysis-of-whispergate-malware/ "Technical Analysis of the WhisperGate Malicious Bootloader") and attempts at account takeover activity by [APT28 & Ghostwriter](https://blog.google/threat-analysis-group/update-threat-landscape-ukraine/ "An update on the threat landscape"), the majority of cyber activity has been regionally specific preparation of the battle space and gives western organizations very little they can do to prepare, let alone respond, not to mention very little to report.

That said it's an unsatisfying thing to tell a customer, especially one who's asking for intelligence, that no news is good news. When folks are glued to news that keeps talking about a difficult geopolitical situation, government agencies won't stop warning of possible cyber attacks, and when every security vendor is posting blog post after blog post about a malware sample they've found (no matter how limited the deployment was) it's almost impossible to answer with "nothing to significant to report".

## Still Nothing... but Significant

So what can you do instead of writing a NSTR intelligence product? Well there are a few options:

* **Focus a product on what you've done, not what you don't know.** Share information about relevant detections and indicators from past reports about related activity or the adversaries in place. As a mentor of mine often said "I don't care about actionable intelligence, I want actioned intelligence". Very few customers really want pure situational awareness, they want the confidence to sleep soundly, not stay up worrying. If you can successfully give them the peace of mind that a threat has been handled you'll have a very happy customer.
* **Write a product about why an adversary isn't relevant, and who they are relevant to.** If an adversary is primarily known for attacking financial organizations and you don't work in a finance related organization call that out. If it's a regional threat and you're out of that region give details. The key is not just saying your organization is irrelevant, but to specifically give the counter examples that are relevant. Counter examples make it easier for a customer to who the victim population is and also who it isn't.
* **Look for more relevant, related issues.** Sometimes a pivot isn't going from DNS to IP, it's going from an irrelevant issue to a more relevant one! [In the current case there is reporting other espionage actors are using Ukraine related lures to conduct their own operations](https://www.forbes.com/sites/thomasbrewster/2022/03/08/chinese-hackers-ramp-up-europe-attacks-in-time-with-russia-ukraine-war/?sh=6db5d5675ee1 "Forbes: Chinese Hackers Launch Attacks On European Officials In Russia-Ukraine War"). Use the request for irrelevant intelligence and shift the requestor to better intelligence.
* **Educate your customers on what good requirements look like.** In all three of these previous cases the problem isn't really bad intelligence, but a bad set of requirements. Henry Ford supposedly once said ["If I had asked people what they wanted, they would have said faster horses."](https://hbr.org/2011/08/henry-ford-never-said-the-fast "Harvard Business Review: Henry Ford, Innovation, and That “Faster Horse” Quote") I don't know if an intelligence analyst has ever said something similar but they certainly could. The key is having the ability and relationship to help customers understand better requirements and lead them to what they need, not what they want.
* **Just say nothing.** An intelligence product that says nothing, especially one thats only take away is "We're monitoring the situation" might be worse than not saying anything. It waters down your readers interest, and risks them ignoring the next product.

None of these strategies are without risk. If a customer comes looking for answers from an intelligence team and doesn't get them they may go looking for answers elsewhere. Measured and accurate isn't always what customers want, and saying _"I don't know"_ or _"NSTR"_ is rarely the RFI answer a customer is looking for.

As in any situation the relationship between an intelligence team and it is customers is a developed over time. As customers know you'll bring them the key pieces of intelligence they need they will eventually also trust when you assess information is not relevant. Until then find the best ways possible to meet the need. The only thing worse than customers asking for bad intelligence is customers who don't ask for any intelligence.

🇺🇦❤️
