---
author: heidiw
comments: false
date: 2019-08-28 19:39:30+00:00
layout: post
link: https://launchdarkly.com/blog/top-3-takeaways-from-the-state-of-devops-2019-report/
slug: top-3-takeaways-from-the-state-of-devops-2019-report
title: Top 3 Takeaways from the State of DevOps 2019 Report
wordpress_id: 194247
categories:
- DevOps
tags:
- Accelerate
- DevOps
- DORA
- state of devops report
---

The [2019 Accelerate State of DevOps](https://cloud.google.com/devops/state-of-devops/) report was published last week. This report is produced by DevOps Research and Assessment (DORA) team, which recently joined Google Cloud. They have collected data for over 6 years and surveyed over 31,000 professionals to gain insight into industry practices and associated business outcomes.

This is such an exciting report for us to read—not just because our product serves DevOps engineers, but because we ourselves are DevOps practitioners and love to see the detailed research and how we compare to our peers. There’s a lot to process in this report, but here are some of the things we found most interesting.


### Move Fast and Please Don’t Break Things


The report’s authors analyze teams and categorize them into four groups based on their DevOps performance: elite, high, medium, and low performers. When they talk about elite performers, they emphasize that those companies deploy 208 times more often than low performers, and can get code changes from commit to deploy 106 times faster. If I told you you could get your work done 100x faster, would you consider it an attractive proposition? This report says that changes in culture and tooling make it possible for organizations to realize those advantages.

I get a lot of pushback when I tell people using traditional development and operations practices that the main advantage of DevOps is speed. They prefer safety to speed, and say their processes exist to prevent bad things from getting pushed out or negatively affecting users. But as we can see from the report, elite performers can recover from an outage or incident 2,604 times faster than the low performers. Since no software process—even the most highly regulated and thoroughly checked ones—is completely free of errors, it is vital to realize that the speed of recovery is part of the story of safety and user protection.

This report also highlights the fact that faster and smaller software changes are less likely to break a system. As you dig into the numbers, you may see that there is an enormous difference between the top 3 groups—elite, high, and medium—and the low performing group. That’s because low-performing organizations are reporting a failure rate between 46% and 60% in answer to this question:


**Change failure rate
**For the primary application or service you work on, what percentage of changes to production or released to users result in degraded service (e.g., lead to service impairment or service outage) and subsequently require remediation (e.g., require a hotfix, rollback, fix forward, patch)?


For those top 3 groups, the problem occurs only 0% to 15% of the time. And as we saw above, those groups fix or remediate any problems that do occur much faster.

Why does this matter to LaunchDarkly? Because one of the easiest and fastest ways to avoid problems in production is to use feature flags to test in production without impacting your users. You will have all the advantages of the unique quirks of the production system—which would never be possible in a staging or test environment—without the risk of accidentally releasing something that’s broken. And if you do release something that needs to be rolled back, a LaunchDarkly flag lets you do that in under a second. That’s going to make your recovery statistics look pretty amazing!


### Reducing Friction


We also found the report’s analysis on “Productivity” to be extremely insightful. At LaunchDarkly, this is a journey we’ve been on ourselves, and we’ve been calling it “Reducing Friction”.

The five pillars of Productivity cited in this report are:



 	
  * Culture of psychological safety

 	
  * Useful, easy-to-use tools

 	
  * Internal search

 	
  * External search

 	
  * (Reducing) Technical debt


Don’t gloss over that bit on psychological safety—it’s key to DevOps culture and improved performance. If everyone on a project feels comfortable bringing up possible problems or reporting glitches, issues are caught much earlier and are easier to correct. If a team member can honestly report what factors played a part in an outage, without fearing blame, the core problems can be addressed, instead of hidden and compounded.

Useful and easy-to-use tools are key to doing business. About 20% of elite performers use “Mainly open source and COTS, with little customization”. That implies that they are adopting the tools that they need, instead of building or heavily adapting them. The more you adapt and tune open-source and purchased software, the more fragile or hard-to-use it becomes.

Also, of the top 3 performing groups, only 5-6% report using “Primarily developed in-house and proprietary to my organization”. Every dollar spent on a proprietary internal tool is a dollar that isn’t spent on making investments in core business value. It’s difficult to keep internal tools updated, and more so to invest in usability and additional features after the initial push to create it.

At LaunchDarkly, we’re investing heavily in both design/usability, and in looking at where the industry is heading to make sure that we are making the features that organizations will need in the future.


### What the Elite Group is Doing


It’s so exciting for us to see how many companies moved from high-performing to elite-performing this year—that group nearly tripled in size! We think that can be attributed to the increased acceptance and full-scale use of emerging best practices for Software Development and Operations (SDO) and productivity including:

**Team-level work**



 	
  * Trunk-based development

 	
  * Continuous integration

 	
  * Automated testing

 	
  * Monitoring/Observability


**Organization-level work**



 	
  * Clear change process

 	
  * Loosely-coupled architecture

 	
  * Code maintainability


**All levels**



 	
  * Disaster recovery testing, including system failovers and some automated production and test “chaos experiments”

 	
  * _Effective_ use of cloud services


Trying to solve the problem of improving end-to-end code quality and speed is hard, but we all have a piece of the puzzle. That’s why the summary of what kinds of DevOps transformations worked is so important.

The report calls out that “high performers favor strategies that create community structures at both low and high levels in the organization”. But Communities of Practice don’t need to be confined within an organization, they can be people across an industry who have similar problems. That’s why Meetups, recorded or live conference talks, blog posts, Twitch sessions, and other forms of peer-to-peer learning are the most effective way for us to grow—both within organizations and as an industry.


### New Standards


DevOps has crossed the chasm, it’s how we’re going to describe the new ways we are working and learning. The ideals of Agile were exploration, efficiency, and minimalism. The ideals of DevOps might be described as speed, safety, and experimentation.

Are you ready to try some new things? It’s gonna go fast, and be fun.
