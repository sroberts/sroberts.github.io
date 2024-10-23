---
title: United States Response to Grizzly Steppe
date: 2016-12-29T06:00:00.000Z
tags:
  - network-defense
  - intelligence
---

![](https://cdn-images-1.medium.com/max/1000/1*Ri5jQN-4b7VoCfINOCXKYA.jpeg)

> Kremlin from the River. Source: [Wikipedia](https://commons.wikimedia.org/wiki/File:Kremlin_27.06.2008_01.jpg).

[Here it is.](https://imgur.com/7drHiqr) After weeks of wondering if and how the United States Government might respond the United States White House, State Dept, Treasury, and US-CERT have released information on and sanctions against the Russian government’s efforts to influence the United States elections. I offer all this without too much analysis given I’ve just seen it myself and expect it will take a long time to digest.

First the technical response, the US-CERTs information which included IOCs and a [Joint Analysis Report with technical descriptions of TTPs](https://www.us-cert.gov/sites/default/files/publications/JAR_16-20296.pdf):

[GRIZZLY STEPPE - Russian Malicious Cyber Activity](https://www.us-cert.gov/security-publications/GRIZZLY-STEPPE-Russian-Malicious-Cyber-Activity)

You can find the [extracted IOCs at the end of the article](https://gist.github.com/sroberts/d77243c9ca4e4038956f8aacaa6b79bb) (_Note: I only did minimal clean up on these. Their usefulness may vary.)_. Ok now that you’re back from checking all those indicators of compromise against your own environment there’s political stuff as well. First we have the best overall government summary from the White House, detailing the whats and whys.

[FACT SHEET: Actions in Response to Russian Malicious Cyber Activity and Harassment](https://www.whitehouse.gov/the-press-office/2016/12/29/fact-sheet-actions-response-russian-malicious-cyber-activity-and)

This also links to the executive order enabling all of this to take place:

[Executive Order -- "Blocking the Property of Certain Persons Engaging in Significant Malicious…](https://www.whitehouse.gov/the-press-office/2015/04/01/executive-order-blocking-property-certain-persons-engaging-significant-m)

Then we get the details, broken out by agency.

## Treasury

> E.O. 13694 authorized the imposition of sanctions on individuals and entities determined to be responsible for or complicit in malicious cyber-enabled activities that result in enumerated harms that are reasonably likely to result in, or have materially contributed to, a significant threat to the national security, foreign policy, or economic health or financial stability of the United States.

[Issuance of Amended Executive Order 13694; Cyber-Related Sanctions Designations](https://www.treasury.gov/resource-center/sanctions/OFAC-Enforcement/pages/20161229.aspx)

## Federal Bureau of Investigation

Taking a slightly different tact the FBI called attention to information on two Russian hackers already wanted for financial cyber crimes. Both were already on the [FBI Cyber Most Wanted List](https://www.fbi.gov/wanted/cyber):

- [FBI: EVGENIY MIKHAILOVICH BOGACHEV](https://www.fbi.gov/wanted/cyber/evgeniy-mikhailovich-bogachev)
  - "Evgeniy Mikhailovich Bogachev is designated today for having engaged in significant malicious cyber-enabled misappropriation of financial information for private financial gain. Bogachev and his cybercriminal associates are responsible for the theft of over $100 million from U.S. financial institutions, Fortune 500 firms, universities, and government agencies."
- [FBI: ALEXSEY BELAN](https://www.fbi.gov/wanted/cyber/alexsey-belan)
  - "Aleksey Alekseyevich Belan engaged in the significant malicious cyber-enabled misappropriation of personal identifiers for private financial gain. Belan compromised the computer networks of at least three major United States-based e-commerce companies."

Quotes pulled from the [White House FACT SHEET: Actions in Response to Russian Malicious Cyber Activity and Harassment](https://www.whitehouse.gov/the-press-office/2016/12/29/fact-sheet-actions-response-russian-malicious-cyber-activity-and). Both are also mentioned in the Treasury Issuance above. Neither _seems_ directly implicated in the Grizzly Steppe intrusions.

## Media Coverage

Some of these seem to be based on coordination with the administration, some seem like follow up stories based on what’s been release.

- [NYTimes: How Russia Recruited Elite Hackers for Its Cyberwar](http://www.nytimes.com/2016/12/29/world/europe/how-russia-recruited-elite-hackers-for-its-cyberwar.html?_r=0)
- [Forbes: FBI 'Most Wanted' Cybercrime Kingpin Linked To Russian Espionage On US Government](http://www.forbes.com/sites/thomasbrewster/2015/08/05/gameover-zeus-surveillance-links/#310abd8e4a29)
- [Reuters: U.S. expels 35 Russian diplomats, closes two compounds](http://www.reuters.com/article/us-usa-russia-cyber-idUSKBN14I1TY)

There were lots of other articles but these seemed most thoughtful and well prepared.

Another interesting side note is the references to the United States authorities taking over physical compounds in the United States used by Russian Intelligence:

## Older References

### Office of the Directory of National Intelligence & DHS

A bit of a throwback but here’s their original statement on the matters:

[Joint Statement from the Department Of Homeland Security and Office of the Director of National Intelligence](https://www.dhs.gov/news/2016/10/07/joint-statement-department-homeland-security-and-office-director-national)

### Senate Armed Services Chairman Senator John McCain

A prominent Republican senator who’s called for investigation and action.

[STATEMENT BY SASC CHAIRMAN JOHN McCAIN ON CYBERSECURITY PRIORITIES IN THE NEW CONGRESS](http://www.mccain.senate.gov/public/index.cfm/2016/12/statement-by-sasc-chairman-john-mccain-on-cybersecurity-priorities-in-the-new-congress)

## Russian Response

This all came out quickly so there has been limited Russian response so far. The most notable quote comes from the [New York Times quoting Dmitri S. Peskov](http://www.nytimes.com/2016/12/29/us/politics/russia-election-hacking-sanctions.html), the spokesman for Russian Prime Minister Vladimir Putin.

> “We regret that this decision was made by the U.S. administration and President Obama personally […] As we have said before, we believe such decisions and such sanctions are ungrounded and illegal from the point of view of international law.”

### Update - 17:12 EDT:

The Russian Foreign ministry has released a statement denying the attacks and denouncing the United States Government response:

[Новости Министерство иностранных дел Российской Федерации МИД](http://www.mid.ru/en/foreign_policy/news/-/asset_publisher/cKNonkJE02Bw/content/id/2581641)

## So what now?

Hard to say. I do know jumping to conclusions is a bad move, so I’ll be writing more after doing some research. To that end here are the IOCs shared by the US-CERT extracted using my [Cacador](https://github.com/sroberts/cacador) indicator extraction tool. I hope they’re useful!

{{< gist sroberts d77243c9ca4e4038956f8aacaa6b79bb >}}
