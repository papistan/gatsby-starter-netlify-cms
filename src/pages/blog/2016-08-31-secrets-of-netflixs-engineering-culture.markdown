---
author: edithharbaugh
comments: false
date: 2016-08-31 17:54:25+00:00
layout: post
link: https://launchdarkly.com/blog/secrets-of-netflixs-engineering-culture/
slug: secrets-of-netflixs-engineering-culture
title: Secrets of Netflix’s Engineering Culture
wordpress_id: 1038
categories:
- Continuous Delivery
- DevOps
tags:
- A/B testing
- continuous delivery
- feature flag
- feature toggles
---

Netflix is not just known for the cultural phenomena of “Netflix and chill”, but for its legendary engineering team that [releases hundreds of times a day in a data-driven culture](http://techblog.netflix.com/2016/04/its-all-about-testing-netflix.html). Netflix is the undisputed winner in the video wars, having driven Blockbuster into the “return” bin of history. Netflix won by iterating quickly and innovating with numerous micro-deployments. Could what worked for Netflix work for you?

Netflix had a virtuous cycle of product innovation. Every change made in the product is with the goal of getting new users to become subscribers. Netflix has a constant flow of new users every month, so they always have new users to test on. Also, they have a vast store of past data to optimize on. Did someone who liked “Princess Bride” also like “Monty Python and the Holy Grail”? When is the right time to prompt for a subscription? Interesting tests that Netflix can run include whether TV ads drive Netflix signups, or whether requiring Facebook to create an account drives enough social activity to counteract the drop in subscriptions from people who don’t have Facebook. If a change increased new user subscriptions, it went into the product. If it didn’t increase new user subscriptions, it didn’t make it in - [hypothesis driven development](https://blog.launchdarkly.com/tag/hypothesis-driven-development/).

However, what if you’re not Netflix? What if you’re a steady SaaS business with 1,000 business customers, on boarding 30 new customers a month? This is a healthy business, doubling in size annually. However what if you wanted to test whether you get more subscriptions with a one step or two step process to add a credit card. With a sample set of 30 a month & 90% current success rate, it will take you three months to determine success. Not everything can be tested at small scale. Tomasz Tunguz talks more about the perils of testing early [here](http://tomtunguz.com/ab-testing-saas/).

The other “gotcha” to watch out for with Netflix style development is obsessive focus on one metric can degrade other metrics. For example, focusing on optimizing new user signup might mean degrading experience for old users. Let’s say that 10,000 customers could be served with “good” speed, or 2,000 with “superfast” speed and 8,000 with “not good speed”. Or 1,000 with lightning fast and 9,000 with terrible speed. You might make the 1,000 new customers very happy, but piss off the 9,000 existing customers and have them quit. A good counterweight is to always have a contra-metric to keep an eye on. It’s okay if it dips slightly if the main metric rises. However, if the other metric tanks, re-consider whether the overall gains are worth it. 

So what lessons can you take from Netflix to help your own business? 

One, have a clear idea of why you’re making changes, even if it’s not something that you can a/b test. Is it to increase stability in your system? Make it quicker for someone to onboard? Know what your success criteria are, even if there’s not a statistically significant “winner”.

Two, break down projects into easily quantifiable chunks of value. Velocity can be as important (if not more important) than always being right. For example if you try 20 small changes, and half are right, you’ll end up 50% better. If you try one big change, and it’s not accretive, you’ll end up with a zero percent gain. Or, as Adrian Cockcroft, Netflix Architect says ["If you're doing quarterly releases and your competitor is doing daily releases you will fall so far behind".](http://a16z.com/2016/09/01/microservices/)

Three, don’t underestimate the importance of your own domain expertise. If you’re constantly testing ideas, even without having enough data, you’re quicker to get into the right path. Let your competitors copy your past mistakes, while you move forward. As Kris Gale, co-founder and CTO of Clover Health said, “You will always make better decisions with more information, and you will always have more information in the future.” But the way to get more information is to iterate. 

_LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER BY HELPING MANAGE FEATURE FLAGS AT SCALE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._


