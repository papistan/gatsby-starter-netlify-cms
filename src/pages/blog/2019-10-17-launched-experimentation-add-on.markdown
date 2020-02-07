---
author: kirani
comments: false
date: 2019-10-17 11:05:45+00:00
layout: post
link: https://launchdarkly.com/blog/launched-experimentation-add-on/
slug: launched-experimentation-add-on
title: 'Launched: Experimentation Add-On'
wordpress_id: 194416
categories:
- Product Updates
tags:
- AB tests
- experimentation
- multivariate feature flags
- product management
---

So your team loves using LaunchDarkly for feature management. Your developers flag all their code and ship continuously. Your operations team feels more confident having a kill switch to manage critical operational systems. Your product managers are excited about controlling how features are released to customers. But then someone drops the question – _"How does this feature impact business metrics?"_ And you're stumped.

Software teams everywhere are trying to optimize for a set of metrics that align with their company's objectives. To help with that, we are happy to announce a powerful new capability for your feature flags – [**LaunchDarkly's Experimentation add-on**](https://launchdarkly.com/features/experimentation).


### Measure your delivery: Feature management and experimentation in one platform


LaunchDarkly's Experimentation add-on enables you to measure the quantifiable improvements your teams are shipping. Now, you can easily turn any feature that's flagged into an experiment and use the results to improve the metrics your team uses to define success.

With LaunchDarkly's Experimentation add-on, you can run multivariate tests that measure the impact of different flag variations on metrics such as _user engagement_ or _system performance_. Collect information about how each variation of the feature performed against the baseline and confidently roll out the best variation to 100% of your users in real-time. No need to redeploy.

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/10/Experimentation_Blog-1024x538.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/Experimentation_Blog.jpg)


### Experimentation use cases


Here's an example: your team has flagged a new clickable banner that allows users to "Sign up for early access features." There are four possible locations in your application where you could place this banner. Your team is unsure which location will be most effective to maximize customer engagement. You create a flag variation for each location of the banner and roll each variation out to 25% of your user base. The flag is turned into an experiment by attaching a metric to count the number of clicks each variation receives. After the experiment collects enough data, it determines a winning variation – the banner location that received the most clicks. You roll the winning variation out to 100% of your users with the confidence of having made a data-driven decision.

It doesn't stop there – we built experimentation with the full-stack in mind. Operations teams, frontend teams, and backend teams can extend their use of LaunchDarkly to now run experiments. You can use experimentation to decide between two different search algorithms or determine if a new feature will increase page load times. Capturing 'numeric metrics' such as _page load time_ or _search results render speed_ lets you measure numeric outcomes for different flag variations and compare them against a baseline value you choose.

[![real-time-updates](https://blog.launchdarkly.com/wp-content/uploads/2019/10/real-time-updates-1-1024x538.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/real-time-updates-1.png)


### How can the LaunchDarkly Experimentation add-on help my team?


LaunchDarkly's Experimentation add-on lets your team:



 	
  * Run multivariate experiments to measure the impact of different variations of a flag

 	
  * Measure full-stack metrics by running experiments for frontend, backend, and operational flags

 	
  * Create experiments that measure conversion metrics or numeric metrics

 	
  * Control when an experiment records data – pause, resume, and reset with the click of a single button

 	
  * Visualize the performance of all the variations over time by viewing experiment charts

 	
  * Designate a population of users to include in an experiment by choosing a subset of them based on flag targeting rules


We built the Experimentation add-on as a natural extension of LaunchDarkly to equip teams with data required to drive their release decisions. With this new functionality, your team is ready to 'learn fast and iterate rapidly' as you confidently ship the best version of your features.


### How to get started with Experimentation


The [Experimentation add-on](https://launchdarkly.com/features/experimentation) is only available to LaunchDarkly customers on Pro and Enterprise plans. To get started with Experimentation, contact your account team at [sales@launchdarkly.com](mailto:sales@launchdarkly.com). Learn more about Experimentation by reading the [Documentation](https://docs.launchdarkly.com/docs/experimentation), and, as always, feel free to email our Product Team at [feedback@launchdarkly.com](mailto:feedback@launchdarkly.com) with your comments and suggestions.

If you're interested in using the Experimentation add-on, we encourage you to check out our ["Nine Experimentation Best Practices"](https://launchdarkly.com/blog/nine-experimentation-best-practices/) post as you're getting started.
