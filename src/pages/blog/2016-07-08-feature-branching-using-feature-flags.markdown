---
author: justinucd
comments: false
date: 2016-07-08 16:05:31+00:00
layout: post
link: https://launchdarkly.com/blog/feature-branching-using-feature-flags/
slug: feature-branching-using-feature-flags
title: Feature Branching Using Feature Flags
wordpress_id: 949
categories:
- Continuous Delivery
- DevOps
tags:
- feature branching
- feature flags
- git
- github
---

Feature branching allows developers to effectively collaborate around a central code base by keeping all changes to a specific feature in its own branch.  With the addition of feature flags, feature branching becomes [even more powerful](https://blog.launchdarkly.com/feature-flag-driven-products/) and faster by separating feature release management from code deployment.


### The Pains of Long-Lived Branching


Traditionally, new development has been done via branching.  These branches typically live for months at a time, with silos of developers attempting to work in parallel.  Long-lived branches often become the “I owe you”  of Gitflow: “I promise to address these merge conflicts… later.”  The pain points that Git was supposed to address -- merge conflicts, missing dependencies, and duplicate code -- gradually emerge the longer a branch lasts.  We then concentrate all the pain of reworks and conflict remedies until the end, which arguably makes the pain much worse.  To avoid these long-lived branching issues, branching with feature flags enables devs to effectively manage short-lived feature branches and continuously deliver better software.


### Feature Branching


To help coordinate development, engineering teams have adopted distributed version control systems (like [GitHub](https://github.com/) and [BitBucket](https://bitbucket.org/)).  These systems allow developers to collaborate within a central codebase and use branches to make updates or develop new features.  [Feature branching](https://www.atlassian.com/agile/branching), therefore, has become a staple of modern development cycles because they allow developers to function without encroaching on each other’s progress. 

One of the shortcomings of feature branching is that feature release management is still tied to code deployments.  In isolation, feature branching forces engineers to manage software delivery within the confines of their version control system.  Non-technical users can’t (and shouldn’t) manage feature visibility and distribution for customers from GitHub.  It is currently not possible for developers to turn features on or off in real-time, as a way to manage risk or gradually introduce a new feature.

[![Feature Branching Without Feature Flags LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/07/Slide1.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/07/Slide1.jpg)

This diagram illustrates how developers create feature branches to manage feature development, ensuring that the current build is always in a deployable state.  While every company’s branching structure will be different, the basic premise is that you branch from a repository to make a new feature.


### Feature Branching Using Feature Flags


This is where the introduction of [feature flags](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic) makes feature branching exceptionally powerful.  Feature flagging allows developers to take full control of their feature lifecycles independent of code deployments.  Application features can be enabled or disabled without requiring code to be reverted or redeployed.

This process is called [feature flag driven development](https://blog.launchdarkly.com/feature-flag-driven-development/), where continuous delivery teams manage feature rollouts separate from code deployments. 

[![Feature Branching With Feature Flags LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/07/Slide2.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/07/Slide2.jpg)

**Benefits**

Feature flagging allows developers to take full control of their feature lifecycles without depending on code deployments.  When you merge a feature branch into master (production), it is already wrapped in a feature flag.  This allows you to deploy the feature “off” and then gradually roll it out to users.  It also allows you to quickly “kill” the feature if it is not working well, without having to redeploy.  Other benefits include:



 	
  * __Better team communication__



 	
  * 

 	
    * 

 	
      * Developers continuously collaborate on new releases, coordinate efforts, and ensure that everyone is moving forward in tandem.









 	
  * __Logical deployments to prevent blocking__



 	
  * 

 	
    * 

 	
      * Deploy code in logical chunks without resorting to long-lived branching.  Even if a feature is not fully ready, it can be flagged ‘off’, but still deployed.









 	
  * __Exposed dependencies__



 	
  * 

 	
    * 

 	
      * Short-lived branching allows you to manage dependencies by removing the ones that are unnecessary.









 	
  * __Faster development__



 	
  * 

 	
    * 

 	
      * Spend less time addressing merge conflicts and refactoring old code.  Spend more time delivering features that users want.









 	
  * __Risk mitigation__



 	
  * 

 	
    * 

 	
      * A feature can be flagged throughout the entire development process, from local, QA, staging, and production.  This means that it can be toggled on or off in isolation, without impacting other development environments.









 	
  * __Manageable code reviews__



 	
  * 

 	
    * Because you are merging more often, code reviews become less tedious and merge conflicts less onerous.







### Better, Together


Modern DVCS combines the benefits of short-lived branches and feature flags.  Tools like GitHub and Bitbucket enable continuous delivery and short-lived branching, while feature flags help make branching faster, less risky, and more manageable.
Therefore, feature flagging does not replace branching, it is complementary and makes it more powerful. Feature branching provides the flexibility to decide when and what to release, while feature flagging lets you take full control of the release itself.  Together, branching and flagging help you maintain and integrate short-lived branches faster and with less risk.
