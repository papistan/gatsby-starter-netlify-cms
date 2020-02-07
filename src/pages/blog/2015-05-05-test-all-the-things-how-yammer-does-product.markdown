---
author: edithharbaugh
comments: false
date: 2015-05-05 21:15:39+00:00
layout: post
link: https://launchdarkly.com/blog/test-all-the-things-how-yammer-does-product/
slug: test-all-the-things-how-yammer-does-product
title: Test all the things! How Yammer does Product
wordpress_id: 87
categories:
- Continuous Delivery
---

_Guest post by Ron Blandford, Yammer Product Manager, describing how Yammer does Product Management_

We still use the [initiative model](http://productman.quora.com/unmanaging-change), described by Drew Dillon. And our development methodology hasn’t really changed since we released [this video](https://www.google.com/url?q=https%3A%2F%2Fvimeo.com%2F66173844&sa=D&sntz=1&usg=AFQjCNHrvtLIGvSKqpN8CL_R6e4q6RI8TA). But neither of these things really describes how we actually do product management here at Yammer. In this two-part series, I’ll first describe how we do product management here at Yammer, then in part 2 I’ll apply that model to a real project

Without further ado...


## Problem Space


Before we build anything, we define the problem space that the feature we want to build will address. Problems are uncovered in myriad ways; we discover them ourselves through daily usage of the product, customers tell us what they’d like to see in the product, engineers make suggestions, other people at Yammer have their own set of problems with the product, etc. Problems can include things like the following:



	
  * Attaching images is really hard on Android and iOS.

	
  * If we want people to work in groups, why do we land people in the Discovery Feed?

	
  * Badge counts are off on the iPhone app.


Ideally the problem space will be small enough that we can address it in a reasonable time, yet large enough that by solving it we will have made a measurable impact on some meaningful metric.


## Research


Once we’ve defined the problem space, we want to make a decision as to whether the problem is worth solving. Every product manager can probably rattle off a dozen things that he or she would want to do at any given time, but obviously you need to prioritize. We rely heavily on our analysts to make these prioritization decisions. In the research phase of a project, some of the questions we might try to answer are:



	
  * Do enough people use this feature for it to be worthwhile?

	
  * What do we gain by solving the problem?

	
  * If we solve this problem, will it change behaviors in such a way as to justify the investment? (Example: if we made files more visible in Yammer, would people post more files? Would they engage more if files were more prominent?)


As product managers at Yammer, we’re extremely fortunate to be able to augment the quantitative insights about user behavior we get from our analysts with qualitative research from our [user research team](http://www.creatingyammer.com/research). This is particularly interesting because data often tells only part of the story. In some cases, we’ll get counter-intuitive results from tests we run; we can always form hypotheses to explain the data, but actually speaking to users is invaluable.


## Design Solutions


Sometimes you’re working on a small project or a small feature, so your design explorations are pretty quick. Other times, you’ll revamp a complicated flow, so the design explorations are more involved. In both cases, designers and product managers work together to come up with a visual or UX framework for a solution to a problem. Through a series of iterations, the framework will go from rough mocks, to refined mocks, to pixel-perfect assets.


## Build it!


We form small teams and tend to do smaller projects. We previously had a 2-10 rule: if a project cannot be completed by 2-10 engineers in 2-10 weeks, then it needed to be broken up into more than one project. We don’t have any hard and fast rules any more, but the sentiment remains. We want to move quickly and we want to know that we’re building the right thing. By breaking things into smaller chunks, there’s less risk that we’ll find out one year in the future that we invested substantial resources into building the wrong thing.


## Test it


Once we’ve built something, we’ll release it behind an A/B Test (or a multivariate test if there are multiple solutions we want to explore). On the web, we usually run tests for about two weeks; on mobile, because we have a smaller user base, our tests tend to run 3 to 4 weeks. The smaller user base forces us to think differently about what and how we test on mobile. If we had to wait 12 weeks to get statistically significant results, we just wouldn’t be moving very quickly. At the end of the day, testing should help us move quickly.

[![testallthethings](https://blog.launchdarkly.com//wp-content/uploads/2015/09/testallthethings.png)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/testallthethings.png)


## Analyze the results


This is one of my favorite parts of my job. In most cases, two or three months would have passed from the time we started thinking about a feature to the time we actually have data to look at. While the goal of our development methodology is to get validated learning, we are human and oftentimes just want to ship our feature.

Sometimes, results are pretty straight-forward and the ship decision is pretty easy. Other times, the core metrics are flat or slightly up/down, so we look at other metrics. Sometimes we look at feature level metrics to better understand the higher level metrics. Either way, our core metric is days engaged. This is the number of times users engaged with our product over a given time period. If a single person posts on web, then checks the mobile app later in the day, that would count as one day engaged. If two different people check the mobile app in a day, that would count as two days engaged.

We believe that days engaged, more than any other metric, is the best indicator of whether a user is getting value out of the product. Everything else, like the number of people who post, the number of messages posted, the number of invitations that people send, retention, etc. can all be very interesting, but if people aren’t using your product, then you have no real metrics to base product decisions upon.


## Ship, iterate, or kill the feature


This tends to be the hardest part of the job. We recently ran an experiment where we added a footer to our daily digest email. The footer was effectively a banner ad asking people to install one of our mobile apps. My expectation was that it would be a slam-dunk type of feature, but it wasn’t. Something like 5.5 million people received this email, but mobile installs in the treatment group were up about 5000 over the control group. As PMs, we expect to be right about ⅓ of the time, neutral ⅓ of the time, and wrong ⅓ of the time. In this case, I was wrong. In the end, even though little to no technical complexity was added, because we didn’t see a change in behavior that was reflected in our engagement number, we didn’t ship the feature. The goal was not to get more installs, but rather to get more people to engage with our mobile apps. Installs were essentially a lever that should have moved days engaged, but they didn’t.

This is truly a collaborative process that requires a lot of questions, delving, digging, investigation, etc. As [Otis Anderson surmised](https://medium.com/@yammerproduct/the-robot-product-managers-are-not-here-f4c17dd5e61b), we shall not soon see the rise of robot product managers.





* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
