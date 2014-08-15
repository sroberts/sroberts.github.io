---
layout: post
title: Crisis Communication for Incident Response
---

One of the parts of incident response that rarely gets a lot of attention in IR circles (though huge attention outside them) is a customer facing victim companies communication to their own customers.

## The 5 Keys to Incident Response Communication

### Be Clear
It's difficult to investigate many intrusions. It's often difficult to explain them, but it remains crucial that the communication about what happened be straight forward. Without this understanding victims will remain confused, and critics will remain skeptical.

### Be Timely
Ok, this one is tricky, likely the trickiest.
- If you communicate too early, before you full understand the intrusion, you have to make lots of follow-ups and seem out of control.
- If you communicate too late your warning is less actionable to victims and thus the impact is even worse.

### Be Actionable
Most people don't care about "XSRF whatever" and "Buffer Over blah blah blah". They want to know what this means to them: what information was exposed and what they need to do to fix it.

### Be Responsible
This is the bitter :pill:, and in todays overly litigious society one of the scariest portions, but also straight forward: Admiting you were wrong and saying you are sorry.

[TODO] ANECDOTE ABOUT DOCTORS SAYING THEY"RE SORRY

### Be Human
Ok, this one is personal, but one of the :key: things I have learned is you can't overvalue a sense of humanity in these communications. This is wildly difficult but crucially important. A feeling that a real person wrote something makes it easier to excuse things taking a bit longer than they could have, or makes the apology believable, instead of just lawyer speak. It's not easy, but it is worth it.

## Done Well: [PF Changs](http://www.pfchangs.com/security/)

The whole idea for this post came out of my initial reaction to [PF Changs breach response page](http://www.pfchangs.com/security/). I'd heard about the breach, and while I haven't been to a PF Changs in a few years I felt it couldn't hurt to check and see if I might be involved. I ended up on a comprehensive page discussing their breach and how it impacted their customers.

| Characteristic | Score | Reasoning |
| -------------- | ----- | --------- |
| Clear | 9/10 | Yes. Especially if you ignore the first big block of text and go to the FAQ style section at the bottom. A map would have made a huge difference. |
| Timely | 9/10 | They lay out their timeline, which makes a big difference.  |
| Actionable | 10/10 | They included the basics all the way to "what to do if you're really mad", and made it easy to figure out if you were involved. |
| Responsible | 7/10 | _"We regret any inconvenience this security compromise may have caused our guests."_  Ok, a bit too "corp speaky" for my taste, but for a big company this is as close as you'll usually get. |
| Human | 6/10 | This is the rarest one to find so they can't really be blamed.* |
| __Total__ | __41/50__ | __Ok, it's a B-, but compare it to other incident responses and this one shines.__ |

## Room For Improvement: Target

I hate to beat a dead horse, I really do, but this was a clear example of how not to do things.

First of all, lets talk about the number of places you need to go to get Targets take on the breach (all based on Googling ```site:target.com breach```):

- [response & resources related to Target's data breach](https://corporate.target.com/about/payment-card-issue.aspx)
- [an update on our data breach and financial perforamnce](https://corporate.target.com/discover/article/an-update-on-our-data-breach-and-financial-perform)
- [Target Confirms Unauthorized Access to Payment Card Data in U.S. Stores](http://pressroom.target.com/news/target-confirms-unauthorized-access-to-payment-card-data-in-u-s-stores)
- [a message from CEO Gregg Steinhafel about Target's payment card issues](https://corporate.target.com/discover/article/Important-Notice-Unauthorized-access-to-payment-ca)
- PDF [GreggLetter-ad-version04.pdf](https://corporate.target.com/_media/TargetCorp/global/PDF/GreggLetter-ad-version04.pdf)
- [credit moitoring FAQ](https://corporate.target.com/about/payment-card-issue/credit-monitoring-FAQ.aspx)

Now these results were in order (whatever that means based on Google's personalization) from only Page 1 of my search.

| Characteristic | Score | Reasoning |
| -------------- | ----- | --------- |
| Clear | 2/10 | Ok... I can tell for sure they were breached. But which of the 6 seemingly relevent articles should I look at first. |
| Timely | 4/10 | Target took the "Communicate early, communicate often" approach. This can work if you're right in your triage. They weren't. Numbers ballooned and they looked unaware and ill informed. |
| Actionable | 4/10 | So it's clear they got breached. But they don't spell that out for consumers. Thankfully it was big enough banks took it into their own hands. |
| Responsible | 7/10 | _"Our top priority is taking care of you and helping you feel confident about shopping at Target, and it is our responsibility to protect your information when you shop with us. We didn’t live up to that responsibility, and I am truly sorry."_ Depends where you look, but this item, from Target's CEO Gregg Steinhafel is contrite and responsible. |
| Human | 5/10 | Depends where you look. There are great examples of Gregg Steinhafel being very human and putting a face on this, there are also plenty of very HR/Legal team statements. It's hit or miss. |
| __Total__ | __22/50__ | Yikes. Far from ideal, but tough to judge given how many places there were to look. Certain bits could have scored very high, but there were too many places to go for information. |

Low score aside it's clear Target did everything in their power to apease a very wide audience. Customer, share holders, regulators, the list goes on and on (PF Changs, it should be noted, is privately held, so they have a significantly less complicated audience). It would have been a massive effort to put everything necessary to all audiences on one page.

