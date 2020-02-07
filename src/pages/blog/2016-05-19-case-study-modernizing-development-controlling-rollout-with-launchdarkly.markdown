---
author: andreaech
comments: false
date: 2016-05-19 17:07:27+00:00
layout: post
link: https://launchdarkly.com/blog/case-study-modernizing-development-controlling-rollout-with-launchdarkly/
slug: case-study-modernizing-development-controlling-rollout-with-launchdarkly
title: 'Case study: Modernizing development & controlling rollout with LaunchDarkly'
wordpress_id: 794
categories:
- Continuous Delivery
- DevOps
tags:
- beta testing
- feature flag driven development
- feature flags
- trunk-based development
---

**The challenge**

The company, a leading online real estate marketplace, sought to bring its development up to date with modern processes. To accomplish this transformation, they hired management with experience at the most idolized mega tech companies.  The first thing on the manager’s agenda? [Move faster, with less risk by using a feature flagging system](https://blog.launchdarkly.com/risk-elimination-and-the-launchdarkly-value-add/) like the one they had built at their previous company.  

Just for some background - at this juncture, the team was doing three-week sprint cycles. They had feature branches that they would develop every three weeks and then push out. They would deploy five features at once and if anything went wrong, they'd have to roll it all back.  

**<!-- more -->The solution**

The senior manager initially thought they’d have to build a feature flagging system from scratch. They were happy to discover LaunchDarkly, evaluate the platform and deem it a viable alternative. The manager assigned a senior engineer to implement it, and LaunchDarkly was rolled out across the company. 

**The results**

Before LaunchDarkly there were endless arguments about what was going to be included in each three-week sprint. There had also been apprehension about waiting too long to ship.  

Now with LaunchDarkly there’s more flexibility and opportunity to experiment and be innovative. When they release a feature, they can roll out to one percent of users at random, check monitoring and make sure everything looks good.  Then, after waiting an hour, they can start ramping it up and roll out to everyone.  They can turn off a feature if they decide it is not ready.  The team is thrilled to be able to release with this kind of precision.   

They can also embrace trunk based development. Formerly, branches were not ideal and got complicated with merges. LaunchDarkly gives them confidence to move to trunk based development, knowing that  - if something is wrong in a feature, they can turn it off without a redeploy so the code path never gets executed.  

In one case in particular, they had planned to rollout at feature to the public, but at the last minute Marketing was unsure of the direction. Instead, they created an invite-only list. With LaunchDarkly they were able to do this quickly and have complete control. They could change course in real-time without affecting anyone's deployment schedule - without getting ops involved. No meetings, no emails, no JIRA tickets. Overall LaunchDarkly has enabled a huge time savings and removed the stress of getting lots of people involved. It's a big win for the company on a human impact level. 
