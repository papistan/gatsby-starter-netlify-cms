---
author: dparzych
comments: false
date: 2019-07-05 17:35:19+00:00
layout: post
link: https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/
slug: best-practices-short-term-permanent-flags
title: Best Practices for Short-term and Permanent Flags
wordpress_id: 194023
categories:
- General
tags:
- best practices
- feature flags
- permanent flags
- short term flags
---

What are best practices when it comes to feature flags? The answer to that as with most questions is “it depends.”



 	
  * It depends on whether the flag is a short-term or permanent flag.

 	
  * It depends on the purpose of the flag.

 	
  * It depends on your specific business needs. What works for one company may not work for you.


This blog series will dive into best practices for feature flags, starting with best practices pertaining to short-term and permanent flags.


## Determine whether you need a short-term or permanent flag


The first recommendation is to determine whether a flag will be a short-term or permanent flag as that will influence future decisions and best practices.


### Short-term flags


A short-term flag has a limited lifespan. Remove the flag once it has fulfilled its business purpose. When thinking of feature flags, most people think of short-term flags. Types of short-term flags include:

**Release:** Slowly exposing a feature to new users—moving from internal users to beta and/or canary users until 100% of users are receiving the feature. When you reach 100% remove the flag(unless it is needed as a circuit-breaker as described below).

**A/B testing: **Segmenting your population to determine a preference for one option over another. Once testing ends, remove the flag, and 100% of users should receive the preferred variation.

**Operational interaction testing:** When rolling out a new microservice, infrastructure component, or third-party tag, a flag can be used to determine the impact on systems. If the CPU spikes or there is a memory leak, or unexpected errors occur, disable the new element while further troubleshooting takes place.

**Kill switches: **A toggle to disable a single feature when things start to go sideways during a release.

After reading those descriptions, you may be thinking that a release flag sounds a lot like an operational interaction testing flag. And they are similar. The primary difference is in who is the controller.  An operational interaction flag is controlled by the ops team to protect the systems where the release flag is controlled by the product or business owner to control how user adoption progresses.


### Permanent flags


A permanent flag is designed to provide control for an extended time after the release of a given feature. In some cases, the flag will be in existence for the life of a feature. Types of permanent flags include:

**Entitlements: **Giving users access to certain features based on a subscription level or authentication status.

**Circuit breakers/Load shedding:** Having the ability to quickly turn a feature off or terminate a connection when problems arise prevents problems from impacting all users. These flags are often activated based on an event. For example, a monitoring tool generates an alert when orders fail to complete. When the alert is triggered, a flag is toggled setting the site to 'read-only.'

**White labeling**: Configuring the look and feel of an application for each client for a white-labeled solution.

**Accessibility: **Allowing users to select which accessibility options and refinements they prefer.


## Feature flag best practices for all flags


Whether you have a permanent or short-term flag, consider these best practices.


### Make flag planning a part of feature design


Feature flags shouldn’t be an afterthought. If you think about feature flags during the design process, you will be setting yourself up for success. Part of the planning includes whether the flag will be a short-term or permanent flag. This decision will then impact other areas such as a naming convention, configuration settings, review and removal processes, and access control and safety checks. We suggest proper planning up front for all flags.


### Standardize naming


You may have a style guide for code with conventions on how to write code for your application that includes things like when and where to use camelCase or the proper use of indentation. These style conventions make it easier to read and understand the code.

Before creating your first flag, come up with a naming convention to be used. Our first recommendation is for verbose flag names, don’t try and be brief. You want people to know what the flag does.  Verbose flag names can be helpful for others to understand what the flag is doing.

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Screen-Shot-2019-06-24-at-1.57.06-PM-300x65.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Screen-Shot-2019-06-24-at-1.57.06-PM.png)

Things to consider when writing the style guide or naming convention.



 	
  * Be descriptive about the flag’s behavior.

 	
  * Include a prefix with a project name or team name.

 	
  * Indicate whether the flag is temporary or permanent.

 	
  * Include a creation date for the flag. (This will be helpful when cleaning up flags, more on this below).

 	
  * Whether or not to use flag in the name. If using a service like LaunchDarkly using flag in the name is redundant. If using a home-grown solution using flag in the name may help clarify the purpose of the code.


For example, you are creating a flag to progressively roll out and test a new chatbox widget of your UI. This will be a short-term flag. Without a naming convention in place, you may end up with a flag called “brand-new-flag” or “new-UI-widget.”

These names don’t tell us a whole lot about this flag. But with a standard naming convention in place that addresses all of the above, you can create a more descriptive flag name like “aTeam-chatbox-widget-temp-030619.” We know from the name, this is a temporary flag for a chatbox widget created by the "a team" on June 3rd, much better.


### Minimize the reach of a flag


The focus of a flag should be small. Having a flag that controls more than one feature action at a time can be confusing and will make troubleshooting issues harder. Think about the smallest unit of logic needed for the most responsive flag. If there are multiple parts to a feature that have to work together, you can create a master flag as a dependency.

For example, say you’re launching a new dashboard in your application. The dashboard has three widgets. You should create a total of four flags: one flag for each widget with a dependency on a fourth flag for the main dashboard. With this scenario, if one widget causes problems the dashboard with two widgets can still be served.


### Review use at regular intervals


Whether you are creating a short-term or permanent flag you need to review flag use at regular intervals. The frequency at which you review the flags may vary based on business requirements and the type of flag. To avoid accrual of technical debt, review both permanent and short-term flags at a regular cadence.

For short-term flags, look to see if the flag has rolled out to 100% of users, or if a flag is served to no users. For permanent flags, examine whether the flag is still needed—was a feature once part of a premium bundle and is now available for all users.

We will cover specific criteria related to removing short term flags below.


## Best Practices for permanent flags




### Establish access control and safety checks


If you have regularly scheduled flag clean-up events, you may worry about the accidental removal of permanent flags. Minimize the risk by implementing access control and safety-checks.

Within LaunchDarkly a flag cannot be deleted without confirmation, but that is a partial solution. There are two additional ways to implement access controls for added peace of mind.



 	
  * Use [tags](https://launchdarkly.com/blog/launched-put-a-tag-on-it/) and custom roles to assign permissions to flags within LaunchDarkly quickly.

 	
  * Set role-based access control (RBAC) to specify who can delete flags in a given environment.


[![](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Screen-Shot-2019-06-24-at-2.02.42-PM-300x130.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Screen-Shot-2019-06-24-at-2.02.42-PM.png)


## Best Practices for Short-term flags




### Create a process for removing flags before you create one


Coding a flag is a two-part process. The act of removing a flag should not be a separate process from the act of creating a flag. As mentioned above, you should plan for flags during the feature design process. This includes the removal of short-term flags. An easy way to handle the removal process is to write a pull request to[ remove the flag at the time you create it](https://blog.launchdarkly.com/how-to-use-feature-flags-without-technical-debt/). Schedule a Github reminder for after the feature is deployed to review and determine if the PR to remove the flag should be committed.


### Conduct regular clean-up and review cycles


Avoiding and eliminating technical debt is necessary. If you don’t pay attention to your flags and conduct regular clean-up and review cycles, you can quickly end up with hundreds or thousands of unused feature flags. Here are some ways to schedule flag clean-up.



 	
  * Schedule time at the end of every sprint to review existing flags.

 	
  * Schedule a clean-up/refactoring sprint at a regular cadence (quarterly, semi-annually, whatever works for your business) to pull out old flags & tags.

 	
  * Make it a competition. Hold a “Capture the Flag” day. The individual or team that removes the most flags wins. (Caution: make sure teams aren’t gaming the system and creating fake flags just to delete them.)


Within LaunchDarkly, we make it easier to identify which flags for removal.

You can:

 	
  * Filter tags by create date to view the oldest flags.

 	
  * View which variations of a flag were recently served. Are 100% of users receiving the same variation?

 	
  * Filter on the last evaluation date of a flag.


Once you have identified a flags for removal, use code references to find all the instances of that flag in your code base.

If not using LaunchDarkly a consistent naming strategy can help you grep the code for instances of flags.


## Conclusion


Although I refer to these as best practices, other practices may be better. These are recommendations that we follow and have heard from other customers. Over time these recommendations may change as we learn more. These should be seen as recommendations and suggestions, feel free to modify and alter based on your specific needs. What works well for one company or team may not work well for another team. Future blogs in this series will cover best practices and recommendations around specific use cases. If there is a best practice you would like to share please drop us a line.



Look for more best practices blogs coming soon:

Operational flags best practices

Release management flags best practices

Experimentation flags best practices

Entitlement flags best practices


