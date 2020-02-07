---
author: zuhaibs
comments: false
date: 2017-09-26 16:29:33+00:00
layout: post
link: https://launchdarkly.com/blog/do-away-with-duct-tape-infrastructure-rollouts-safer/
slug: do-away-with-duct-tape-infrastructure-rollouts-safer
title: 'Do Away with Duct Tape: Infrastructure Rollouts a Safer Way'
wordpress_id: 2038
categories:
- Continuous Delivery
- Feature Management
tags:
- ElasticSearch
- feature flags
- infrastructure
---

So I was told I need to write an introductory blog post for my first week at LaunchDarkly. Two months later and here I am writing my intro post. Seems like I got a little carried away writing code before getting to this! My name is Zuhaib and I will be working as Software Developer on anything back-end related. Previously I worked for a small startup called Atlassian on a chat product called HipChat.

Feature flags are not something new to me. I’ve seen a few homemade solutions in the past that always seem to leave me wanting more from them. Most systems would let you turn on or off features but had very limited ability to target users or control the percent rolled out. It was at Atlassian I got my first exposure to LaunchDarkly. We switched from our first in-house solution to LaunchDarkly and it was great. It helped us get new features out faster to our customers, and more importantly control features and backend service and disable them if they started to act up.

And as expected, we at LaunchDarkly do a lot of the same, using advance feature flags to make sure LaunchDarkly users have a good experience. One way we do that is by controlling rollout of infrastructure changes like database migrations. 

Recently we needed to test an upgrade of our ElasticSearch cluster without impacting users. So we used a [[percentage rollout]](https://support.launchdarkly.com/hc/en-us/articles/115002409248-Controlled-and-percentage-rollouts) in LaunchDarkly and slowly targeted a subset of our users to the new cluster while we watched performance and stability.[![](https://blog.launchdarkly.com/wp-content/uploads/2017/09/Screen-Shot-2017-09-21-at-11.01.29-AM-1024x769.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/09/Screen-Shot-2017-09-21-at-11.01.29-AM.png)

Our flag allows us to control which cluster gets writes, which cluster gets reads, or which gets both. If we find a problem, we disable the flag and users go back to the other cluster. If it's performing well we increase the percentage of users using the new database. You can see today we have rolled out the new cluster to 75% of users and working on getting it up to 100%. The code for this is as simple as adding a new statement that writes to either or both clusters:

    
    if flags.WriteEsA || !flags.WriteEsB {
      # Write to cluster A
    }
    if flags.WriteEsB && esConfigB != nil {
      # Write to cluster B
    }
    


While we may only be evaluating this second cluster for a short period of time, we’re actually leaving the flag in place, as it gives us a clean control mechanism for recovering from backups, or performing major version upgrades to ElasticSearch without customer impact.

This is just one of the many things you can do with LaunchDarkly flags for infrastructure changes.
