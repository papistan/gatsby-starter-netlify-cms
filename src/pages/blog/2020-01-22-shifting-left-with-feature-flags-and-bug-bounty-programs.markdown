---
author: ctarquini
comments: false
date: 2020-01-22 16:05:36+00:00
layout: post
link: https://launchdarkly.com/blog/shifting-left-with-feature-flags-and-bug-bounty-programs/
slug: shifting-left-with-feature-flags-and-bug-bounty-programs
title: Shifting Left with Feature Flags and Bug Bounty Programs
wordpress_id: 194860
categories:
- DevOps
tags:
- application security
- bug bounty
- debugging
- feature flags
---

In this blog post, we're going to cover a method to reduce your risk exposure by leveraging [feature flags](https://launchdarkly.com/features/feature-flags/) and your existing bug bounty program. Our goal is to catch and patch more bugs before attackers have a chance to find them.


*** * ***


The internet has become a very hostile place. It seems like every day there's a headline featuring another data breach or compromise. Companies are now the shepherds of an ever-growing inventory of personal data, sensitive secrets, and business-critical services.

In the internet of now, you simply can't afford to leave application security to chance. Forget to sanitize one little input or leave a subtle logic bug in play, and it could cost you and your customers immensely.

According to a [study by IBM](https://www.ibm.com/security/data-breach), the average cost of a data breach worldwide is just shy of $4 million. In the United States, the average cost nearly doubles to **$8.19 million**.

It has never been more critical to integrate security into your SDLC (software development life cycle). A mature application security program is crucial to preventing the many vulnerabilities that attackers exploit to gain a foothold in your infrastructure.


### The application security funnel[![application-security-funnel](https://blog.launchdarkly.com/wp-content/uploads/2020/01/application-security-funnelx2.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2020/01/application-security-funnelx2.jpg)


Generally, a mature application security process will look something like this. As you move down the funnel, there should be fewer vulnerabilities present in your code.

The closer we are to the red zone, the closer we are to these vulnerabilities being in production, where the race is on for you to find vulnerabilities before an adversary does. The longer bugs remain in the red zone, the higher your chances of seeing your company’s name in an unfavorable news headline.


### Bug bounties


_A bug bounty program is a deal offered by many websites, organizations, and software developers by which individuals can receive recognition and compensation for reporting bugs, especially those pertaining to exploits and vulnerabilities._
_– Wikipedia_

As far as bug huntin' goes, you can consider bug bounty programs as the last line of defense. While some companies do offer pre-production environments for researchers, more often than not these researchers are pen testing against production.

One of the major advantages that bug bounties bring to the table is a huge pool of researchers with varying skill-sets and methodologies that can augment your existing teams at a low cost.

Unfortunately, it's hard to reap these benefits before adversaries find your bugs. Moreover, creating a separate environment just for researchers can be expensive and complicated to maintain. On top of that, if your separate environment does not exactly replicate production, you may end up leaving some bugs hidden by divergent conditions/configurations.


### Feature flags


_[Feature flags] allow you to manage components and compartmentalize risk. You can do pretty cool things like roll out features to certain users, exclude groups from seeing a feature, A/B test, and much more._
_– FeatureFlags.io_

If you're not familiar with feature flags, I highly recommend checking out these introductions from [featureflags.io](https://featureflags.io/feature-flags/) and [LaunchDarkly](https://launchdarkly.com/benefits/). Overall, the idea with feature flagging is that you separate the release of a feature or change from code deploys by gating them behind a flag.

You can think of feature flags as a policy-based decision that returns one of many variations. In its simplest form, a flag may be a Boolean decision where a flag is a simple **true** or **false**. It may look something like this:
[![feature-flag-example](https://blog.launchdarkly.com/wp-content/uploads/2020/01/Screen-Shot-2020-01-21-at-10.38.10-AM.png)](https://blog.launchdarkly.com/wp-content/uploads/2020/01/Screen-Shot-2020-01-21-at-10.38.10-AM.png)

Example policies would be to change the decision the feature flag engine returns based on user tags such as **beta_user** or performing a canary rollout where the flag returns **true** for 50% of users and **false** for the rest.


### Bringing it all together


By combining feature flags with your existing bug bounty program, you can significantly reduce your exposure to critical security vulnerabilities.

It's fairly common for researchers to have tagged accounts when participating in bug bounty programs already. This is especially true of private programs on platforms such as [HackerOne](https://hackerone.com/).

With that machinery in place, you simply make a new rule when evaluating your feature flags so that security researchers will have access to your shiny new changes before the public does.


#### Targeted feature release


[caption id="attachment_194864" align="aligncenter" width="2246"][![launchdarky-bug-bounty-rules](https://blog.launchdarkly.com/wp-content/uploads/2020/01/launchdarky-bug-bounty-rules.png)](https://blog.launchdarkly.com/wp-content/uploads/2020/01/launchdarky-bug-bounty-rules.png) Example targeting rule in LaunchDarkly that enables a feature for security researchers along with employees and QA testers.[/caption]

Now that the feature is only returning **true** for security researchers, there are only a few things left to do:



 	
  * Determine a timeline for how long you will leave the feature available only for security researchers.

 	
  * Communicate with your security, development, and operations team and make sure you have resources available to triage and remediate the reports and maintain good response times on your reports.

 	
  * Let the folks who hold the purse strings know that you're expecting a higher number of reports during this time.

 	
  * Announce the feature to your bug bounty participants. I'd highly recommend offering a time-bounded bonus payout for all reports related to this new feature to further incentivize researchers to put this young code through the gauntlet.




### What have we gained?


For a fairly low cost, you have made great strides in reducing the number of vulnerabilities available for adversaries to find. You have made it so researchers can pen test changes _before_ they become generally available – yet another layer of defense between you and the headlines.
