---
author: heidiw
comments: false
date: 2017-11-10 02:30:29+00:00
layout: post
link: https://launchdarkly.com/blog/measure-twice-launch-once/
slug: measure-twice-launch-once
title: Measure Twice, Launch Once
wordpress_id: 2089
categories:
- Continuous Delivery
- DevOps
tags:
- continuous delivery
- DevOps
- secure deploy
- secure release
- security
---

You want all your developers to have access to the main trunk of code to deploy — that’s the point of trunk-based development. It’s important they can put their code out as often as they want and iterate on their projects. However, you don’t always want developers turning on features that will have customer impact without some way to reverse course.

Secured activation is an under-appreciated part of feature management. Your developers can deploy code whenever they want—but when it comes time to test it externally, or turn it on for everyone, you can use settings to make sure that only a select group of people has the permissions to do so. All the activation changes should be tracked and audited to ensure that all activations have an accountability chain.

At LaunchDarkly, we have found that it’s good to be permissive about who can use and create feature flags, and restrictive about who can activate them. If you are trying to get started with transitioning to using feature flags more broadly, you might want to think about how to [implement a repeatable process](https://blog.launchdarkly.com/feature-flag-transition-setup-guide/). You might also want to leverage LaunchDarkly’s ‘[Tags](https://docs.launchdarkly.com/docs/managing-a-feature-flag#flag-settings)’ feature to help with the organization and custom roles to assist with [delegation and access](https://docs.launchdarkly.com/docs/custom-roles).

You want the following qualities in people who have the permissions to change your user experience:



 	
  * Understands the business reason for making the change

 	
  * Has the technical knowledge or advisors to know when the code is ready to go live

 	
  * Has a process in place for making the change and then testing it


You don’t want to have only one person who can do this, because they’ll inevitably become a bottleneck. Make sure your process can keep releasing even if a key team member is unavailable. 

In the beginning you may look to put a process around every change and then look for optimization in that process. However, over time you should look into determining  what level of change merits process and what can be executed more easily. In some cases this might even allow for small changes to be approved or executed by individual engineers. Usually, features that have anything to do with money, user data collection, or changes in the user process should have a formal approval process. Changes to backend operations can be quieter and therefore need less formal process and lean more heavily on automated testing and peer review.

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/11/BIG-RED-BUTTON-225x300.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2017/11/BIG-RED-BUTTON.jpg)

Think about your current deployment process. What happens if someone releases something too early? How do you protect against that? How will you port that control over to the access control that LaunchDarkly offers? What is the failure case if something doesn’t launch properly?

Feature flags are easy to implement in code, but managing them well across an organization takes some planning and forethought.
