---
author: heidiw
comments: false
date: 2018-01-12 23:30:55+00:00
layout: post
link: https://launchdarkly.com/blog/what-makes-a-failure-a-disaster/
slug: what-makes-a-failure-a-disaster
title: What Makes a Failure a Disaster?
wordpress_id: 2169
categories:
- DevOps
tags:
- continuous delivery
- DevOps
- failure
- risk reduction
---

It was December 31, 1999, and a young sysadmin had just bet her boss that their systems wouldn’t go down. The stakes were her job. She was driving 4 hours to go to a New Year’s Eve party with her friends, and she wasn’t worried about Y2K.

Though our sysadmin had her pager, if something went down in her systems she wasn’t going to be able to fix them before people noticed. Her boss told her that if anything happened, she didn’t need to come back, ever. She left anyway, because she knew everything would be fine. This wasn’t an act of faith, it was that she knew nothing would go down, because for the whole of 1999, and even before, the system had been preparing.

Everyone knew Y2K was coming. Our sysadmin had patched all her scripts, and installed all the software updates the vendors had said, and traced back every piece of hardware and firmware to make sure it had been patched and updated.

As we have moved further from the reality of Y2K, we have forgotten. We forget just how many millions of dollars and person-hours went into reducing our risk. Utilities did fail, but that was in July of 1999, because groups were doing planned tests. They even staggered the tests so the whole grid wouldn’t go down. The SEC threatened to cut off non-compliant banks if they didn’t meet a series of rolling upgrade deadlines. Thousands of programmers were hired to remediate systems that couldn’t be automatically upgraded.

Now it’s easy to think Y2K was an overblown story. Nothing really terrible happened, so it must not have been that bad. But it _was_ that bad, and we just managed to fix it in time through an effort more intense and widespread than putting humans on the moon. Often we know that things will fail, but what makes a failure a disaster?


### Risk Reduction


In the case of Y2K, all the upgrade focus was about [risk reduction](https://blog.launchdarkly.com/risk-reduction-and-harm-mitigation/). We knew there was something that could cause problems, so we did everything we could to prevent it from happening—from preventing a major disaster from occurring.

While it’s impossible to avoid all risk, we recognize that we can at least reduce risks that we’re aware of. But what are the essential elements of reducing risk? And how do we know what we need to prevent?


### Secure Your Zone


Rather than becoming overwhelmed at the idea of trying to avoid risk, we need to break our world into zones, decide how much risk we can tolerate in each zone, and then secure it as much as possible.

In my job, I work on adding documentation to our APIs. There is a risk I could break someone’s integration if I add or delete something in the wrong place. To avoid that, we have a process where someone else reviews my changes before they go live.

Pull requests and reviews are so standard that we don’t usually think of them as a risk reduction strategy, but they are. We are adding a little friction to the act of committing code in order to prevent easy mistakes. We also prevent mistakes or malicious activity by limiting who has “commit bits” to critical parts of our code, and by keeping backups of our code so that we can restore a working state quickly.

At LaunchDarkly, we care about reducing risk by making it easy to do the right thing and hard to make unrecoverable errors. Wrapping feature code and product settings in feature flags makes it easy to change the state of your software without adding the confounding effects of a deployment to the process.

Your zone is only as big as the area you have control over. You want to be sure that people who are changing your software are authorized to do so. I can change the APIs and their documentation, but no one has or should give me access to change other parts of our code.


### Predict States


Another way to reduce risk is to address issues before they become problems by evaluating your system and identifying where they might occur. To predict the states something could end up in is formally known as finite state machines (FSMs). An FSM is defined by a list of its states, its initial state, and the conditions for each transition from one state to another. Many process flowcharts are a state machine for systems.

To use a state machine to assess risk, you enumerate all the possible states your system could be in, and what would make that happen. You can then address the transitions that lead to states you don’t want.

After code is committed, there are still several ways it could fail. For instance, we try to have more than one way to serve it, so that if there is some kind of infrastructure problem, we have a second server in another location already online. Sometimes, the risk is that the page or product won’t work for everyone, so we deploy it to just a small percentage of our users—also known as a canary launch. That means that if there was a risk we didn’t foresee, we only have to repair a small part of our user base, not the whole thing.

Being able to test our assumptions on a small scale gives us the confidence that our predicted states are accurate and we can handle them.


### Make Low-Stakes Bets


We can’t entirely avoid risk and stay safe. One of the ways we can reduce risk is to make small bets—not all-or-nothing—but a little bet that this will go well, or at least generate a minor improvement. Risk is not an all-or-nothing proposition, it’s a matter of what we can tolerate, what we can afford to lose. Once we can define that for ourselves, we can be much more adventurous within those limits.
