---
layout: post
title: Crisis Communication for Incident Response
description: 'Because sticking your head in the sand is not an option.'
---

One part of intrusion response that rarely gets enough attention in DFIR circles is the communications victim companies make to their own customers. This is almost always the only real information the public (and even security community) see about an intrusion and communicating what happened effectively is crucial to minimizing damage, both to customers and to your organizations reputation.

## The 5 Keys to Incident Response Communication

### Be Clear
It's difficult to investigate many intrusions. It's often even more difficult to explain them, especially to less technical individuals, but it remains crucial that the communication about what happened be straight forward, ideally limited to a 5th grade reading level. Without this understanding victims will remain confused and critics will remain skeptical. This clarity has to go beyond one message by making sure messaging stays consistent across multiple messages and mediums.

### Be Timely
Being timely providing information is a double edge sword:

- If you communicate too early, before you full understand the intrusion, you have to make lots of follow-ups and seem out of control.
- If you communicate too late your warning is less actionable to victims and thus the impact is even worse.

Its a fine line to walk. In the end the best option is often to over communicate and assume the worst. It's far better to retract a statement saying "It wasn't as bad as we initially thought..." than to continually have to say "Actually it's worse than we thought...".

### Be Actionable
Most people don't care about _"XSRF whatever"_ and _"Buffer Over blah blah blah"_ [geek speak](https://www.youtube.com/watch?v=7BpsXZpAARk). They want to know what this means to them: what information was exposed and what they need to do to fix it. Whether it's needing to setup credit monitoring or rolling credentials a notification needs tell victims what they need to do to protect themselves going forward. They key is to be clear about two courses of action:

- What is the affected organization doing to protect customers going forward?
- What can affected customers do to protect themselves?
- __Bonus Points:__ What is the affected company doing to make sure this never happens again?

### Be Responsible
This is the bitter pill, and in today's overly litigious society one of the scariest portions, but also straight forward: Admitting you what you did wrong wrong and saying you are sorry. This may seem like a parent's advice to a child, but even surgeons are resorting to this kindergarten strategy:

> But with malpractice premiums soaring and a national patients' rights movement pushing for full disclosure of medical errors, the industry is rethinking the traditional approach known as "defend and deny." Stories [...] are persuading a growing number of hospitals, doctors and insurers that apologies may end up saving some of the huge sums paid out to settle disputes over medical care.

[Wall Street Journal: Doctors' New Tool To Fight Lawsuits: Saying 'I'm Sorry' ](http://online.wsj.com/news/articles/SB108482777884713711)

### Be Human
Ok, this one is a personal preference, but one of the key things I have learned is you can't overvalue a sense of humanity in these communications. This is wildly difficult but crucially important. A feeling that a real person wrote something makes it easier to excuse things taking a bit longer than they could have, or makes the apology believable, instead of just lawyer speak.

It's not easy, but it is worth it. One of the easiest way to do this is by making sure that all communications go through a single point of contact. This allows communication to have a face as well as a voice.

## Done Well: [PF Changs](http://www.pfchangs.com/)

The whole idea for this post came out of my initial reaction to [PF Chang's breach response page](http://www.pfchangs.com/security/). I'd heard about the breach, and while I haven't been to a PF Chang's in a few years I felt it couldn't hurt to check and see if I might be involved. I ended up on a comprehensive page discussing their breach and how it impacted their customers.

| Characteristic | Score | Reasoning |
| -------------- | ----- | --------- |
| Clear | 9/10 | Yes. Especially if you ignore the first big block of text and go to the FAQ style section at the bottom. A map would have made a huge difference. |
| Timely | 9/10 | They lay out their timeline, which makes a big difference.  |
| Actionable | 10/10 | They included the basics all the way to "what to do if you're really mad", and made it easy to figure out if you were involved. |
| Responsible | 7/10 | _"We regret any inconvenience this security compromise may have caused our guests."_  Ok, a bit too "corp speaky" for my taste, but for a big company this is as close as you'll usually get. |
| Human | 6/10 | This is the rarest one to find so they can't really be blamed. |
| __Total__ | __41/50__ | __Ok, it's a B-, but compare it to other incident responses and this one shines.__ |

## Room For Improvement: [Target](http://www.target.com/)

I hate to beat a dead horse, I really do, but Target's breach response was a clear example of how not to do things.

First of all, lets talk about the number of places you need to go to get Target's take on the breach (all based on Googling ```site:target.com breach```):

- [response & resources related to Target's data breach](https://corporate.target.com/about/payment-card-issue.aspx)
- [an update on our data breach and financial perforamnce](https://corporate.target.com/discover/article/an-update-on-our-data-breach-and-financial-perform)
- [Target Confirms Unauthorized Access to Payment Card Data in U.S. Stores](http://pressroom.target.com/news/target-confirms-unauthorized-access-to-payment-card-data-in-u-s-stores)
- [a message from CEO Gregg Steinhafel about Target's payment card issues](https://corporate.target.com/discover/article/Important-Notice-Unauthorized-access-to-payment-ca)
- [<i class="fa fa-file-pdf-o"></i> GreggLetter-ad-version04.pdf](https://corporate.target.com/_media/TargetCorp/global/PDF/GreggLetter-ad-version04.pdf)
- [credit monitoring FAQ](https://corporate.target.com/about/payment-card-issue/credit-monitoring-FAQ.aspx)

Now these results were in order (whatever that means based on Google's personalization) from only Page 1 of my search.

| Characteristic | Score | Reasoning |
| -------------- | ----- | --------- |
| Clear | 4/10 | Ok... I can tell for sure they were breached. But which of the 6 seemingly relevant articles should I look at first. [Brian Kreb's articles](http://krebsonsecurity.com/2013/12/sources-target-investigating-data-breach/) were far more  straight forward. |
| Timely | 4/10 | Target took the "Communicate early, communicate often" approach. This can work if you're right in your triage. They weren't. Numbers ballooned and they looked unaware and ill informed. |
| Actionable | 4/10 | So it was clear they got breached but they don't spell out what that meant for consumers. Thankfully it was big enough news banks addressed the problem themselves and reissued cards. |
| Responsible | 7/10 | _"Our top priority is taking care of you and helping you feel confident about shopping at Target, and it is our responsibility to protect your information when you shop with us. We didn’t live up to that responsibility, and I am truly sorry."_ Depends where you look, but this item, from Target's CEO Gregg Steinhafel is contrite and responsible. |
| Human | 5/10 | Depends where you look. There are great examples of Gregg Steinhafel being very human and putting a face on this, there are also plenty of very HR/Legal team statements. It's hit or miss. |
| __Total__ | __24/50__ | __Far from ideal, but tough to judge given how many places there were to look. Certain bits could have scored very high, but there were too many places to go for information.__ |

Low score aside it's clear Target did everything in their power to appease a very wide audience. Customers, share holders, regulators, the list goes on and on (PF Chang's, it should be noted, is privately held, so they have a significantly less complicated audience). It would have been a massive effort to put everything necessary to all audiences on one page.

## In the End
Every incident is different and requires its own communication plan. There are always complications, be they legal, regulatory, industry, or self imposed. Whats key is to focus on clarity, timeliness, actionability, taking responsibility, and ultimately showing victims that there is a human on the other side of the keyboard who understands the situation and is on their side.

If you want to see a really well done response that hits on all 6 characteristics I recommend reading basically any After Action Report/Crisis Communication by [Digital Ocean](https://www.digitalocean.com)'s [Mark Imbriaco](https://twitter.com/markimbriaco). The man ~~could~~ should write a book on this subject.

![How to Write a good post mortem ](https://pbs.twimg.com/media/Bq1hkICCQAATgEz.png)

See [this Mark Imbriaco post mortem example](https://github.com/blog/1796-denial-of-service-attacks).

_Thanks to [Rachel Vandernick](https://twitter.com/VandernickR) of [WebpageFX](http://www.webpagefx.com) for her feedback as a crisis communications & PR professional._
