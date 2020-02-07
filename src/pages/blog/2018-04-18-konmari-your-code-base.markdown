---
author: heidiw
comments: false
date: 2018-04-18 16:03:42+00:00
layout: post
link: https://launchdarkly.com/blog/konmari-your-code-base/
slug: konmari-your-code-base
title: Konmari Your Code Base
wordpress_id: 2491
categories:
- DevOps
tags:
- DevOps
- feature flags
- feature management
- konmari
- software development
- tagging
---

Konmari is a new name for an old concept—we shouldn’t live with STUFF that isn’t serving a purpose in our lives. It’s championed by [Marie Kondo](http://konmari.com/), a woman passionate about throwing things away and organizing what’s left. Her breakout book was titled “The Life-Changing Magic of Tidying Up.”

Though Kondo’s focus leans heavily on physical things, I think her concepts are important for our digital lives as well. Because storage is effectively free, we never feel the pain of being hoarders, at least not directly. Never throwing things away is a personal choice when it's about blurry pictures of our cats in our own folders, but it’s a different problem when it’s about our code base.

How do you know when you should remove flags from your code base? How do you clean up after all your experiments?


### Build for Future Ease


The easiest way to avoid having big messes to clean up is to not make a mess in the first place. We all know that sounds simpler than it is, but I also believe that any improvement is a help. Just as it’s better to put your dirty clothes in a laundry hamper than on the floor, it’s better to [tag](https://blog.launchdarkly.com/tag/tagging/) new features with meaningful identifiers. Here are some best practices for future ease. You may already know them, but just in case:



 	
  * Add [comments](https://blog.launchdarkly.com/launched-comments-adding-context-to-your-actions/) about what the code is meant to do

 	
  * Add uniform [tags](https://blog.launchdarkly.com/tag/tagging/) for search-ability

 	
  * Use meaningful [variable names](https://blog.launchdarkly.com/launched-enterprise-feature-flag-management/)

 	
  * If a feature is dependent on another function, mention that in the [comments](https://blog.launchdarkly.com/launched-comments-adding-context-to-your-actions/)

 	
  * Add dates about when something was added, don’t just depend on commit messages to indicate that




### Automate Deletion


We have emotions about deleting things. We have to accept that at some point the feature (or picture or paragraph) will no longer serve a purpose. Since the things we delete always represent memory, potential, or work, we are often reluctant to delete them—we know that moment in time will never happen again or that work would have to be repeated.

The solution to this is not to avoid deleting things, but to avoid the emotional impact of making the decision. Automate the deletion of anything that you can. Meeting notices vanish when the meeting is past–deployment flags should evaporate when the feature is fully adopted. By configuring your code to delete outdated elements, you keep the clutter from accumulating in your codebase.

Consider being even more radical—if you have a policy of only supporting a certain number of versions, automatically roll the oldest version off support when you release a new version. If you make it a policy, everyone will know that they must upgrade when a new version is coming out.


### Cultivate Tidy Habits


_Wash on Monday. Iron on Tuesday. Bake on Wednesday…_

This was an old expectation about when housework happened. Have some set times in your development cycle for cleaning up after yourself. What about that hour at the end of the workweek when you don’t want to start anything? Or the day you have mostly blocked off for sprint exit/entry? Those are good natural break points to go in and clean up the things you have been meaning to get to. When the cadence is regular, you’ll better remember what you were doing. Making cleanup a regular chore instead of a “when I get to it” behavior means it’s much less annoying when you do it.


### Reward good behavior


Are you the sort of person who internally yells at yourself (or others) for making mistakes? Consider a new way of training yourself to do the right thing. Instead of being angry or frustrated about mistakes, catch yourself doing the right thing and reward it. Deleted some old code? Stand up and look at the sun, or have a hard candy, or trigger a micropayment to a fun account—whatever you find motivational. Associating good behavior with something you enjoy makes it easier to keep doing the good behavior. Even if you know what you OUGHT to do, most people don’t get a dopamine hit from fulfilling obligations.
