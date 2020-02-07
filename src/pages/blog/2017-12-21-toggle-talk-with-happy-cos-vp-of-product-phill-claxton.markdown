---
author: andreaech
comments: false
date: 2017-12-21 22:08:32+00:00
layout: post
link: https://launchdarkly.com/blog/toggle-talk-with-happy-cos-vp-of-product-phill-claxton/
slug: toggle-talk-with-happy-cos-vp-of-product-phill-claxton
title: Toggle Talk with Happy Co's VP of Product Phill Claxton
wordpress_id: 2127
categories:
- Continuous Delivery
- DevOps
tags:
- continuous delivery
- DevOps
- feature flags
- HappyCo
---

Phill Claxton has implemented feature flags in three different organizations. As a driving force on the business side, he’s seen his company evolve and witnessed firsthand the difference feature management has made in the overall progress of the company. When it comes to the most fundamental benefits of feature flagging, he points to continuous delivery and the speed of learning. Phill is VP of Product at HappyCo, COO at Storekat.com and a cross-functional consultant for early startups.


### **How long have you been feature flagging?**


I've been a fanboy of feature flags for a little while. They're a strange thing to love but it's the result of implementing them that has made such a huge difference in my life, and the companies I've been involved with.

I think I can trace my first exposure back to a [HubSpot article](http://product.hubspot.com/blog/how-we-built-our-stack-for-shipping-at-scale) in 2015. We were faced with a challenge at a startup that I founded down here in New Zealand called DeskDirector. We had maybe 150 - 200 customers/accounts at the time, and we were hitting a challenge that’s a telltale sign for those on the other side of learning about feature flags. We had a very small development team, and it was very hard for us to do multiple things. We needed to decide what to build next and measure the impact from it.

We had made some pretty substantial failures, it'd be fair to say. We’d launch features that we thought were going to help the many but when they failed we realized it was the false wisdom of the few.


<blockquote>“So we were trying to work out a way to learn faster.”</blockquote>


At the same time we were thinking about how we can restructure our pricing, and it sort of came together when we read that Hubspot article. We realized we needed to control the release of features we were working on to cohorts of customers. That way we could quickly decide whether this had the broader appeal to launch to our greater market.


### **When do you think feature flagging is most useful?**


Once you hit that 100 customer mark there's some natural segmentation that lend itself to feature flagging to test out cohorts. The customer grouping starts to look about the same as it will at 1,000 customers. I would suggest that’s probably when you want to start really thinking about feature flagging.

I'd caveat that by saying we were in the B2B space. You might get there much sooner if you were selling a product to consumers.


<blockquote>“That being said—the last times we’ve done it, it was always too late. We could have started earlier. I suggest you start learning really early without worrying too much about cohorts.”</blockquote>


For me it's always been two things, which is about continuous delivery and the speed of learning. Specifically, allowing a product team or engineering team, to launch something and learn at a much faster rate from the customer base. The same thing goes for pricing inside your product.

In the SaaS world, the need to experiment with pricing is a part of your standard business practice. And the earlier you can do that, the better. Sometimes people forget that there's many different use cases for feature flagging.


### **Are there any cases where feature flagging is not a good idea?**


Our practice was to flag anything that was impacting on the user's experience. So, if the impact on the end-user experience is low and there's a very high level of confidence in the change, then we're comfortable not flagging. If the change itself is completely hidden from the users' experience and service side, then that's not normally something that we would need to consider feature flagging.


<blockquote>“I would say more often than not there are situations where it isn't thought of enough. The default position should be that it is flagged.”</blockquote>




### **Best use of a feature flag—a personal story?**


By this stage we were feeling mature in our development cycle and had flagging in place. It was a documentation platform that tracked expirations of devices that an IT company was looking after.

We were working on a new notification engine which would trigger expiration alerts to customers. And so we did feature flag this feature, and we'd gone through a lot of initial wireframes with customers. We’d even built out an early stage MVP without production data. All was looking great, and we launched it into production. It was feature flagged and enabled only for those in our Customer Advisory Council.

The moment we did that every single one of them had their inboxes flooded with anywhere from a few hundred to, in one case, about 15,000 emails. We'd built this notification engine to let them know when things were about to expire and embarrassingly we didn't think about what was going to happen when things had already expired. And so every device they were managing, which counted, for many, into the thousands would suddenly trigger this alert to say, "This is about to expire"—when it actually already had. And so that was one of those cases where we went, "Hallelujah." We had gone through a lot of exhaustive QA and unit tests, etc., so we knew things weren't going to break and the upside was our notification engine worked at a massive scale. It still had a lot of work to do when we turned it on.

The reality was that the output for the end-user was certainly not the experience we would've wanted. If we had turned it on at the time to our north of 2,000 customers, we would've flooded our support team with a lot of requests. Also we would had a lot of very unhappy users.

“So because of feature flags we were able to quickly go back and amend that feature then test again with that Customer Advisory Council before launching as a general release.”

The real benefit obviously came from all the learning that we got from the process as well. Not just for problems, but also just day-to-day functionality that we thought we’d scoped correctly, when given to customer in production, it's totally different.


<blockquote>“This is when the real learning happens. Showing them some wireframes is totally different from showing them it working with their data.”</blockquote>




### **What do you think is the number one mistake that’s made around feature flagging?**


The #1 mistake for me would be implementing it and actually not remembering to ensure that the features being built are actually flagged. It sounds simple, but it's actually a common trap that happens all too frequently. You end up not flagging enough of the functionality in the product and it becomes more work later on.

#2 You need to flag more often than you probably were planning to.


<blockquote>“You need to ask yourself why are these features not being flagged rather than the other way around.”</blockquote>


Probably the only other thing is not having a program for removing flags as well. For all the benefit it offers it does make your code base a lot more verbose, and there's a small amount of arguable tech debt that you're buying with all this. So not having a program for removing the flags is probably the other mistake.


### **How do you think feature flags play into the DevOps movement? Continuous Delivery?**


Early last year I started a company called IT Glue, as the Chief Operating Officer. And I would certainly say that feature flags would be one of those reasons we were able to scale and scale so fast. We went from 500 accounts and about seven on staff, to 2,500 accounts and 63 staff within one year. So you often get asked, how were you able to scale? What's the magic bullet?


<blockquote>“And I'd never say there was a silver bullet, but if I listed off the ten things that drive towards continuous delivery, a dev process supported by feature flags would always be on that list.”</blockquote>


They're really a very critical part of DevOps. Having not worked in very large engineering teams I can only imagine what the impact would be and I would say it plays a fairly substantial role. But it tended to be our DevOps engineers who gained some of the best advantages from actually having these feature flags in place.


### **Are you seeing feature flagging evolving? If so how? And how do you expect it to change in the future?**


I've certainly seen companies like LaunchDarkly launch into the market, which is great. So much of what was having to be done in-house is now can be managed by third parties. It's definitely evolving, yes. I'm not seeing the evolution of it, not for the fault of anyone else, happening fast enough though. Part of the challenge, I think, is that the greater majority of companies I speak to still don't really know and think about feature flagging as an important part of their growth strategy and engineering strategy.

Know a feature flag enthusiast we should talk to? [Email us](mailto:hello@launchdarkly.com) or let us know on [Twitter](https://twitter.com/LaunchDarkly).
