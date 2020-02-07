---
author: edithharbaugh
comments: false
date: 2016-05-30 20:48:26+00:00
layout: post
link: https://launchdarkly.com/blog/gluecon-2016-developer-operations-tools-teams/
slug: gluecon-2016-developer-operations-tools-teams
title: 'GlueCon 2016: Developer + Operations, Tools + Teams'
wordpress_id: 854
categories:
- DevOps
tags:
- CircleCI
- continuous delivery
- DevOps
- GlueCon
---

GlueCon is a low-key, practitioner focused developer conference near Boulder, Colorado. Docker had been announced at a prior GlueCon, and so the conference has a well-deserved reputation as to where the next breakthrough will be announced. In a two-day conference with six tracks per day, you could “choose your own adventure” to learn about relevant tools for your domain of “Cloud, DevOps, Mobile, APIs, Big Data”, or get exposed to techniques outside your usual realm. I was amazed by how many people I thought I knew, then realized they looked familiar from their Twitter handle. However, if you’re looking for Dreamforce or the CES of Software, this is definitely NOT it - which I liked. 

My favorite talk was [Travis Vachon](https://twitter.com/tvachon), Engineering Director of CircleCI on “DNA of Successful Development Teams”. The room was packed to the rafters, with people sitting on the side railings.  My main takeaway was 

https://twitter.com/edith_h/status/735600564340326400

 [Emmanuel Paraskakis](https://twitter.com/manp), VP Product at Apiary.io talked about trying to get developers to write consistent APIs by providing them with a style guide full of “musts” and “should” for format. “No one read my 20-page style guide”. I think we’ve all been there.<!-- more -->

https://twitter.com/edith_h/status/735573245714276352

 Brian Carpio gave a good overview of tying DevOps back to Lean and Agile. His thesis was that Agile has sped up development such that the bottleneck became Ops, and a bottleneck, in the Lean world is “waste” as code accumulates without being functionality in the real world. Then ShadowIt happens as groups spin up their own servers to avoid being dependent on a slower Ops team. Very true, I’ve seen it happen. Paul Bruce of Perfecto Mobile talked on a subject dear to my heart- continuous delivery and rollbacks. “Testing verifies correctness, rollback mitigates risk”. 

https://twitter.com/edith_h/status/735581394177429505

It’s not an either / or decision - you can test and still want the ability to rollback, and even with the ability to rollback, you should still do some level of testing. [Aren Sandersen](https://twitter.com/arensand) showed some cool techniques to lock down access dynamically - for example, only allowing the active PagerDuty engineer to access a production system. 

https://twitter.com/edith_h/status/735955118521090048

[Rob Hirschfeld](https://twitter.com/zehicle) talked about being able to deploy to different cloud servers and did a daring live demo. He said, “AWS sets the patterns, but maintain portability.” He also defended hybrid clouds, saying, “Operators run data centers from habit, scar tissue & good reasons”.

[Joe Beda](https://twitter.com/jbeda) was a few years ahead of me at Harvey Mudd College, so of course I attended his talk on Identity. Joe Beda, a longtime Google leader, said people make the assumption that whatever Google does will just work for them “Google For Everyone”. In reality, Google, having been around for almost 20 years now, has technical debt and tangled dependencies, just like everyone else. He showed Mudd practicality in using “domain driven naming” for his new project SPIFFE - the domain was available, so that’s what he named it. 

https://twitter.com/edith_h/status/735916286073405441

I gave a standing room only talk on Faster Feedback with Feature Flagging. Though it was a vendor-neutral talk on how feature flagging can help developers move faster with less risk, I was pleased that Travis, CircleCI Director attended and during the Q & A said, “Don’t build this yourself - buy LaunchDarkly”, and tweeted 

https://twitter.com/tvachon/status/735885222898634752

It wasn’t all lectures, there were many opportunities for meeting up with old and new colleagues.  #gluerun, was a 6:30 AM 6 mile run, at over a mile high with views of the Rockies. [Dan Wendlandt](https://twitter.com/danwendlandt), Rob Hirschfeld, [Kelly Taylor](https://twitter.com/ktinboulder) and I talked about reversibility, mitigating risk, and why long running branches are “poison”. There’s nothing like running uphill at altitude to distill my thoughts to the bare essence. I only had to play the “let me stop to tie my shoe” (and catch my breath) card once.  [Seth Goings](https://twitter.com/sethgoings), Deis VP Engineering, told me about the joys and challenges of managing an open source product over lunch. The Buoyant team told me some of their horror stories with poorly managed feature flags. It was cool to meet a Digital Ocean engineer who said, “I know you, I listen to your podcast”. [Jeremy Edberg](https://twitter.com/jedberg) hauled the SF group into Denver for a fun supper, where I got to hear more feedback from CircleCi on how they use LaunchDarkly. SAP had a root beer kegerator (very good root beer) and at the end of the conference raffled off a kegerator (not the one they used, another one). 

It seemed like there was no single breakout tool this year - I heard both that “serverless is very hot” or “the serverless track is sparse”. People thought IBM Watson was amazing, but Seth who’d been to GlueCon for four years said, “I think we’re still digesting the prior breakthroughs”. All in all, a friendly, well run conference I’d highly recommend. 

_Disclosure: LaunchDarkly is a customer of CircleCI, and CircleCI is a customer of LaunchDarkly. Apiary is a customer of LaunchDarkly._
