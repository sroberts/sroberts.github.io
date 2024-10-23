---
title: ACH Analysis of a Trump Campaign Compromise
date: 2016-12-12T05:00:00.000Z
tags:
  - intelligence
---

> **_ASIDE:_** This post gets political. People may agree or disagree based on their own experience or personal belief. I accept that. I’m attempting to use evidence and analytical rigor to reach my conclusions while averting my own bias. If you think I missed the mark on those aspects (evidence or rigor) feel free to reach out to me. If you just disagree with my conclusions then I’d love to see a blog post exploring your own evidence and process.

The news this past week has been filled with statements about claims and counter claims of whether or not Russia was involved in meddling in the 2016 Presidential Election. Intelligence agencies, news outlets, & security vendors have stated that Russia compromised the Democratic National Committee, [Hillary for America campaign Chairman John Podesta](https://hillaryspeeches.com/2016/10/12/hfa-statement-on-report-that-fbi-suspects-russia-behind-hack-of-podestas-emails/), Democratic Congressional Campaign Committee, and others related to the campaign. During the debates Donald Trump questioned the validity of this, leading to the _400 lbs hacker_ line (and resulting [Twitter accounts](https://twitter.com/real400lbhacker)) and he and his transition team have repeatedly questioned/refuted all such claims, even suggesting that the entire intelligence community might be wrong.

What’s been more interesting to me though has been questions about whether or not the Republican National Committee and Donald J. Trump for President, Inc were victims of similar attacks (For brevity we’ll just refer to them all collectively as the Trump Campaign). Many of us working in intrusion detection and incident response have had conversations with peers from other companies in the same vertical describing identical attacks. In fact this is one of the major strengths of computer network operations: hacking represents an asymmetric threat, having relatively low variable costs (the effort to compromise a target) vs fixed costs (the development of exploits and tools). I will say I for one assumed that the same attacks directed at the Democratic institutions were also directed at the Republican institutions.

The Republican leadership has said little about any of this until this weekend:

[NBC News - Priebus on Russia's Influence: 'I Don't Know Whether It's True'](http://www.nbcnews.com/meet-the-press/video/reince-on-russia-s-influence-i-don-t-know-whether-it-s-true-830288963631)

I for one was hugely surprised to hear not simply the assertion that the Trump Campaign hadn’t been hacked (an absence of evidence not being the same as evidence of absence), but the unabashed confidence. I realized that this surprise (even incredulousness) was based on my own experience and assumptions, biases I have, instead of on any analytic rigor. Sunday morning with coffee is obviously the best time to apply intelligence rigor to a problem, so here goes.

One powerful analytic model for problems of conflicting information and rampant bias is [Analysis of Competing Hypotheses](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis/art11.html). A system of listing important information and scoring it to weed out bias and develop relativistic scoring of likely possibilities. ACH doesn’t give _the answer_ but helps analysts understand what is most likely. _Descriptions of each step are pulled from the CIA’s Center for the Study of Intelligence article linked above._

### Hypothesis

> _Identify the possible hypotheses to be considered. Use a group of analysts with different perspectives to brainstorm the possibilities._

I can come up with five serious hypotheses specifically with regard to Russian intelligence gathering activity:

- The Trump Campaign was compromised and they are unaware.
- The Trump Campaign was compromised and they are aware but want to withhold it.
- The Trump Campaign was not compromised because their security was so good it blocked all attempts.
- The Trump Campaign was not compromised because no one attempted.
- The Trump Campaign was not compromised because the adversary was collecting via non-technical means (IE HUMINT).

These don’t cover 100% of all possibilities (like if the adversary has a time machine and is getting intelligence sent from the future) but covers the major possibilities.

### Evidence

> _Make a list of significant evidence and arguments for and against each hypothesis._

Next we collect evidence for and against our hypotheses. Evidence is based on publicly disclosed information and some are based on experience from 10+ years as a defender and incident handler. Some of it is circumstantial, but it’s the best we have to go off of.

#### The Trump Campaign was compromised and they are unaware

- [Most organizations are compromised in some way.](http://www.verizonenterprise.com/resources/reports/rp_DBIR_2016_Report_en_xg.pdf)
- Political campaigns are inherently difficult to protect.
- [The adversary has used CNO against political targets before.](https://www.dni.gov/index.php/newsroom/press-releases/215-press-releases-2016/1423-joint-dhs-odni-election-security-statement)
- The adversary has used CNO for political influence.

#### The Trump Campaign was compromised and they are aware but want to withhold it

- Political campaigns are rich targets full of policy level information.
- Successful compromises is seen as an organizational failure.
- It is particularly important for Republicans to be seen as strong on National Security.

#### The Trump Campaign was not compromised because their security was so good it blocked all attempts

- Network & Host Intrusion Detections are avoidable by skilled adversaries.
- Rince Priebus (RNC Chairman) has stated the FBI investigated the Trump Campaign networks and found nothing.

#### The Trump Campaign was not compromised because no one attempted

- The intelligence community, vendors, and FBI stated the DNC hack was compromised by RU CNO.
- Adversaries commonly target multiple organizations in the same vertical.

#### The Trump Campaign was not compromised because the adversary was collecting via non-technical means (IE HUMINT or collaboration)

- [Donald Trump has spoken positively on RU President Vladimir Putin.](http://www.cnn.com/2016/07/28/politics/donald-trump-vladimir-putin-quotes/)
- [Donald Trump is accused of having many undisclosed ties to Russia.](http://time.com/4433880/donald-trump-ties-to-russia/)
- Campaigns have a large number of minimally vetted people involved.

### Matrix

> _Prepare a matrix with hypotheses across the top and evidence down the side. Analyze the “diagnosticity” of the evidence and arguments–that is, identify which items are most helpful in judging the relative likelihood of the hypotheses._

Taking the theories and evidence above everything goes onto a matrix without any editing or scoring. Fields have been abbreviated or coloquilized layout.

![Initial ACH Matrix](https://cdn-images-1.medium.com/max/800/1*lqsmNsdoDP9Z0uB6Gb5-sw.png "Initial ACH Matrix")

Looking at the matrix a handful of pieces of evidence stand out as diagnostically significant:

- _Adversaries commonly target multiple organizations in the same vertical._ They often have similar information and similar vulnerabilities. There’s no reason to think the defense of one political campaign would be better or worse than another. They are all resource limited and trying to provide similar capabilities.
- _Donald Trump is accused of having many undisclosed ties to Russia._ While this hasn’t been confirmed or denied by the President Elect there are many [many](https://www.washingtonpost.com/politics/inside-trumps-financial-ties-to-russia-and-his-unusual-flattery-of-vladimir-putin/2016/06/17/dbdcaac8-31a6-11e6-8ff7-7b6c1998b7a0_story.html?utm_term=.724950758ee5) [many discussion about DJT having deep business ties to Russia](https://www.bloomberg.com/news/articles/2016-07-27/quicktake-q-a-the-trump-putin-bond-that-may-or-may-not-be-real). His current rumored Secretary of State [Rex Tillerson is also accused of having deep financial relationships in Russia](http://money.cnn.com/2016/12/11/investing/rex-tillerson-exxon-russia-putin/index.html).
- _The intelligence community, vendors, and FBI stated the DNC hack was compromised by RU CNO._ This is probably the biggest key to the whole issue and is confirmed by a wide variety of sources ([1](https://www.bloomberg.com/politics/articles/2016-08-11/fbi-said-to-have-high-confidence-russia-behind-democratic-hacks), [2](https://www.crowdstrike.com/blog/bears-midst-intrusion-democratic-national-committee/), [3](https://www.wired.com/2016/07/heres-know-russia-dnc-hack/)).

### Refine Matrix

> _Refine the matrix. Reconsider the hypotheses and delete evidence and arguments that have no diagnostic value._

Here we add and remove a few pieces of evidence.

- **Removed:** _DJT is positive on Putin_ as this is sort of redundant with DJT closeness to Russia and could over influence.
- **Added:** _Vulnerable Campaign Infra_. There are reports during the campaign as researchers looked at the security of Trump Campaign systems. This includes out of date servers and lacking security measures like two factor authentication. While many of these may have been fixed this came far after the attacks against DNC and thus likely periods of actor focus on campaigns. [Motherboard: Donald Trump Is Running Some Really Insecure Email Servers](https://motherboard.vice.com/read/trump-is-running-some-really-insecure-email-servers) & [Twitter: @GossiTheDog](https://twitter.com/GossiTheDog/status/788148795716542464)

![Refined ACH Matrix](https://cdn-images-1.medium.com/max/800/1*sxop8hdqqGb6Xl1dCEe_ig.png "Refined ACH Matrix")

I didn’t change my hypotheses. I still feel strong about all of them.

### Tentative Conclusion

> _Draw tentative conclusions about the relative likelihood of each hypothesis. Proceed by trying to disprove the hypotheses rather than prove them._

Now the process moves on to scoring. The scale is +2 to -2. The +2 should indicate a very strong correlation, -2 means a strong contradiction. A score of 0 indicates evidence neither confirms or denies the hypothesis.

![Tentative Scored ACH Matrix](https://cdn-images-1.medium.com/max/800/1*KfLF0QOd7Yk28DsWmukidA.png "Tentative Scored ACH Matrix")

This isn’t the end yet! Now it moves on to the adjustment of bias.

### Adjust for Bias

> _Analyze how sensitive your conclusion is to a few critical items of evidence. Consider the consequences for your analysis if that evidence were wrong, misleading, or subject to a different interpretation._

This one is tough and requires considerable self reflection.

- _Rince Priebus (RNC Chairman) has stated the FBI investigated the Trump Campaign networks and found nothing._ This piece of evidence sways everything pretty far and relies heavily on taking Rince Priebus at face value. Given that the validity of his statement is at the core of the whole exercise this may be a bad piece of information to rely on.
- _The adversary has used CNO against political targets before._ This is another very influential piece of information, however it should not be removed. This is backed up by multiple sources and while it moves the analysis across the board that’s because it’s an important piece.

What about consequences if evidence is incorrect? In some cases this could have a fairly dramatic swing. A particularly high amount of weight is placed on the evidence that the Democratic campaign institutions were compromised. Given this has been confirmed by multiple sources I’m comfortable with that. Similar issues arise with the assumption that campaign infrastructure is likely vulnerable, but this is also supported with considerable evidence. That said a change to either of these would cause a significant shift in probability, but would not ultimately change the outcome of the analysis.

### Finalize & Synthesize Analysis

> _Report conclusions. Discuss the relative likelihood of all the hypotheses, not just the most likely one._

Now our final matrix. Again, it’s based on a number of experience based assumptions and facts we have available.

![Finalized Scored ACH Matrix](https://cdn-images-1.medium.com/max/800/1*qU-z07KeQw3Hj8k3w1N-Eg.png "Finalized Scored ACH Matrix")

Based on this analysis I have a moderate confidence that the Trump Campaign was the victim of offensive computer network operations, but it is unclear whether or not the leadership was aware. It seems highly unlikely that the Trump Campaign had either perfect security or was not targeted at all. Non-CNO collection is difficult to determine based on the evidence we have available.

One thing I do know is that none of these items being true are good things.

- If _the Trump Campaign was compromised and they are unaware_ then they have no idea how bad the damage could be. This seems most likely.
- If _the Trump Campaign was compromised and they are aware but want to withhold it_ then we are being lied to, either to protect their own ongoing investigation (which seems unlikely given the lack of leaks) or in an act of hubris to prevent us from knowing how bad it really is.
- If _the Trump Campaign was not compromised because their security was so good it blocked all attempts_ then the technical security lead should start a company and put us all out of business (I find this personally the least likely possibility by miles).
- If _the Trump Campaign was not compromised because no one attempted_ then either they had nothing of value to steal which seems bad or…
- If _the Trump Campaign was not compromised because the adversary was collecting via non-technical means_ then the campaign either had a traitor in their midst without knowing or were sharing sensitive information deliberately, neither of which are good things.

I’ve wracked my brain trying to come up with more possibilities but I’m at a loss. I’ve long subscribed to the idea _“Never assume malice where ignorance will suffice”_ but when it comes to electing our officials and leading our country neither seems acceptable to me.

### Future Analysis

> _Identify milestones for future observation that may indicate events are taking a different course than expected._

How could this analysis improve in the future?

- Further technical reporting released either by vendors.
- Leaks from inside the Trump Campaign.
- [Declassification of relevant intelligence.](https://www.wyden.senate.gov/download/?id=D12DD589-5800-4BEF-9F93-A0A122F38D29&download=1)
- Better insight into HUMINT or collaboration between the Trump Campaign and the Kremlin.
- More information may be released by other political campaigns, either from the primary or 3rd parties.
- All of this has been based on the assumption of an intrusion by Russian CNO. There are many other countries with viable CNO teams that may have also targeted various campaign entities. Activist attacks are also within scope of consideration.

Whether or not we get any of these there are plenty of unanswered questions.

### My Conclusion

It’s unlikely anyone will ever know the full truth and this analysis is likely missing key information, it merely provides a framework to understand what we do know. Hopefully this demonstration shows how an organization can use ACH to understand complicated issues. This may become even more important in the future as we have to accept that political realities, domestically and internationally, are a part of the computer security world.
