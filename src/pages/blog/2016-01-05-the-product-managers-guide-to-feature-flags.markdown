---
author: justinucd
comments: false
date: 2016-01-05 09:01:59+00:00
layout: post
link: https://launchdarkly.com/blog/the-product-managers-guide-to-feature-flags/
slug: the-product-managers-guide-to-feature-flags
title: The Product Manager's Guide to Feature Flags
wordpress_id: 302
categories:
- Continuous Delivery
- Feature Management
tags:
- continuous delivery
- empathy
- feature flags
- feedback
- product management
- product manager
---

### The Product Manager


You are the king (or queen) of the product.  You're the engineer, the designer, the business mind, the marketer... in fact, you are a little bit of everything.  You are the product owner, but more importantly, you are the leader.

In his article, Prasad Thammineni (CPO of Choose Energy) outlines the [9 qualities of a great product manager](https://www.linkedin.com/pulse/20140410232440-137353-9-qualities-of-a-great-product-manager):



	
  1. **Strategic Thinker**

	
    * Understanding the current needs of the product and how it fits with the company's overall vision




	
  2. **Passion for Products**

	
    * Love what you make, love what you do.




	
  3. **Empathizes with the Customer**

	
    * Respect and understand the customer's wants and needs.




	
  4. **Interviews Customers**

	
    * Gather insights from your customers, learn their pain points and discover opportunities




	
  5. **Aspires to Build Great Experiences**

	
    * Understands that user experience is paramount for product success




	
  6. **Keeps Score**

	
    * Identify the key metrics and track performance, establish baselines to measure success




	
  7. **Ability to Prioritize**

	
    * Keep things in order, understand what needs to be completed first and what needs to wait.  Use customer feedback for prioritization.




	
  8. **Collaborative Leader**

	
    * Management is a collaborative process, you cannot be dictatorial and expect to inspire your team.




	
  9. **Execution**

	
    * Action-oriented, you get things done.





To embody these 9 principles, you'll typically see PMs use a myriad of tools to organize teams, manage development, QA, and track benchmarks (JIRA, Aha, Mavenlink, and about 10,000 others).  Every aspect of effective product management seems to come with its own suite of tools, except for two: **Customer Empathy** and** Customer Feedback (Interviews, testing)**, which I'll explore in greater depth.


### Empathy


As a Product Manager, you must empathize with the needs and wants of your target audience.  As [Catherine Shyu](https://medium.com/@cthrin/empathy-a-product-managers-key-to-success-462686e9e77f#.f4z5ef5i8) (PM at FullContact) writes, "The product manager is responsible for knowing the customer like the back of their hand — their frustrations, their daily thoughts, the context in which they use the product, and their needs."   It's one thing to ask your customers for feedback, to interview them during development, and to have them test your product before it's launched.  It's another thing to have your customers test your product in a real environment or to provide certain customers with a personalized experience.

A key to empathy is the ability and capacity to take action on feedback.  As [Jennifer Winter](https://www.usertesting.com/blog/2015/04/27/practical-empathy-on-demand-webinar/) notes, "Collaborative and creative empathy doesn’t equal sympathy. The goal of empathy is to support and understand the intent and purposes of others, which in turn will help you obtain insightful feedback."


### Genuine Feedback


User interviews, in-person testing, assigning tasks, and conducting basic user research are fundamental to development a successful user experience.  However, they each have a common limitation: artificial feedback.

When we sit down with a user and ask he or she to do something, we have taken that user out of their natural environment by forcing them to unnaturally provide feedback.  The feedback we receive is still valuable, but it's not purely genuine.

**Genuine feedback** comes from testing real users in a real environment without them knowing they are being tested.  Imagine being able to test a new feature or experience to 1% of your real users before launching it to the rest? Actions often speak louder than words.  If I rolled out Feature A to 1% of my users with the hypothesis that they will use it and then they don't.. or they use it once and then never again.. that feedback is deafening.  Now, imagine if you could just roll back Feature A completely and then use interviews/testing to figure out why the feature wasn't being used, and then roll it out again.

[Feature flag driven development](https://blog.launchdarkly.com/feature-flag-driven-development/) enables this genuine feedback loop.

[![Product Management with Feature Flags](https://blog.launchdarkly.com/wp-content/uploads/2015/12/ff_benefits_infographic-683x1024.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2015/12/ff_benefits_infographic.jpg)




### 




### Feature Flags & Genuine User Feedback


PMs at Google, Facebook, and Amazon have [integrated feature flags into their development cycle](https://blog.launchdarkly.com/secret-to-googles-engineering-culture/). This has enabled them to know how users react to a new feature before it has been released to everyone.  It also helps them be more responsive to feedback without having to leave a 'bad feature' out on the market for too long.

Let's say Facebook wants to release a new timeline feature called Timeline Beta.  This feature reorders timeline stories in order to increase user engagement.  Timeline Beta has gone through all the rigors of internal testing, user interviews, and whole gamut of proper UX research.  For launch, Facebook wraps Timeline Beta in a feature flag, allowing Facebook to have complete control over who sees the feature.  On day 1, they roll out the feature to 0.5% of Facebook users to see how they like it.  On day 2, they see a 20% decline in user engagement for those users who had Timeline Beta.  On day 3, Facebook rolls back Timeline Beta via the feature flag and begins the cycle anew.

[![iterative_rollout](https://blog.launchdarkly.com/wp-content/uploads/2015/12/iterative_rollout.png)](https://blog.launchdarkly.com/wp-content/uploads/2015/12/iterative_rollout.png)

Imagine if Facebook released Timeline Beta to all of its users without an easy mechanism to revert to the previous version.  They could have seen millions in lost revenue, caused a social media uproar, and turned users away.  This is the power of feature flag driven development: the ability to take full control of who sees your new features and to test those features in a real world environment.


### Getting Started with Better Product Management


Integrating feature flags into your development cycle does not require a complete process transformation or months of retraining.  If you're already practicing continuous delivery, feature flagging can become an integral part of your dev cycle in a week.

While there are many [open source feature flag resources](http://featureflags.io/resources/), they require some substantial integration effort and internal management - and often do not satisfy the performance demands of an enterprise product.

LaunchDarkly's [feature flags as a service](https://blog.launchdarkly.com/featureflagasservice/) is used by PMs at [BEHALF](https://www.behalf.com/), [Auction.com](http://auction.com), and [CircleCI](https://circleci.com/) to manage their feature flag driven development cycles.  If you'd like to learn more, check out [LaunchDarkly](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic) to see how it works.
