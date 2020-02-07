---
author: edithharbaugh
comments: false
date: 2015-07-23 22:47:17+00:00
layout: post
link: https://launchdarkly.com/blog/hypothesis-driven-development-yammer-case-study/
slug: hypothesis-driven-development-yammer-case-study
title: 'Hypothesis Driven Development: Yammer case study'
wordpress_id: 106
categories:
- Continuous Delivery
tags:
- a/b test
- hypothesis driven development
- Yammer
---

_How Yammer does hypothesis driven development, guest post by Ron Blanford, Yammer Product Manager_

Recently I kicked off a project to overhaul to our iPhone publisher in order to make it easier for users to post photos to Yammer. We didn’t start this project with the intention of overhauling the entire publisher, but when we took a closer look at the overall experience, we knew we needed to make big changes.

We still maintain a lean startup mentality at Yammer, which means we develop a hypothesis and build the most minimal thing we can to test that hypothesis and validate our decisions with data incrementally. As you might imagine, overhauls that change many variables at once are not too common around here but sometimes we know they are necessary to drive the product forward. According to Mary Meeker’s Internet Trends 2014, 1.8 billion photos were being posted to social media sites on a daily basis. So we generally know that people are accustomed to taking pics from their phone and posting them to social media sites. People have pictures on their phone. We just weren’t making it easy for them to post those photos to Yammer.


## Go Big or Go Home


Why was it necessary to overhaul the publisher? I didn’t need an analyst or a user researcher to tell me that the experience of posting photos to Yammer was terribly outdated. Just using the feature made it obvious that we hadn’t invested in this part of the app in years. You’d tap the camera icon, which would then prompt you to choose to take a new photo or upload an existing one, at which point you’d get dropped into your photo roll or the camera. If you wanted to post multiple photos, you’d have to go through the flow again, and again, and again. As a general rule, we want to minimize the opportunity for bad experiences in the product, but we’d also been hearing from our customers through our user researchers that they were having difficulty with the photo posting process. This is especially true for retailers, for example, who employ thousands of workers who don’t sit in front of a computer every day. These users rely primarily on the mobile experience to communicate with their coworkers, and sharing photos is an important use case.


## Hypothesis


My hypothesis for this project was that if we made it easier to post images, people would indeed post more images, and as a result, the number of days our users engage with Yammer would go up. Why? We know that posts with images are more engaging than those without. Posts with a photo get on average 17% more responses and nearly four times as many likes. Why are replies and likes important? Likes provide validation, acknowledgement, and support from the network. They encourage people to post more, which in turn encourage more replies, likes and eyeballs. It’s a nice reciprocal engagement loop that ultimately leads to more content on the network, more people having conversations, more people getting work done, more people discovering things, etc.

[![IMG_8118](https://blog.launchdarkly.com//wp-content/uploads/2015/09/IMG_8118.jpeg)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/IMG_8118.jpeg)


## Build It


This was the easy part for me since the vast majority of my heavy lifting was done prior to any developers writing a line of code. From here on out, our publisher was mostly in the hands of the designer and developers.

What made this project different from so many others was that it required really close attention to what would otherwise be thought of as small details. Whereas transitions and animations are often afterthoughts to the core parts of an app or feature, in this case, they were core to our success. If the transition was jumpy or unnatural, people would find the new experience jarring and painful. If we didn’t nail the experience, people would get frustrated and find other ways to share their photos. Many hours were spent dealing with how the keyboard slid out, how the gallery slid in, how the full-size gallery took over the whole screen, and more. We’ve always had amazing talent at Yammer; in this project, I believe the skill of our designers and developers allowed us to deliver a product of exceedingly high quality in a very short period of time.


## Test It


In general, we show an experiment to the fewest number of users possible because this allows us to get statistically significant data from the smallest pool of users. In the event the feature is a bad experience or just doesn’t test well, we will have disrupted fewer people than we otherwise would if we tested everything at 50/50. On mobile, however, because our usage is so much less than web, the smallest group of users is invariably 50%. So we ran this as a standard 50/50 A/B test.


## Analyze the Results


Initial results were showing no significant effects. So we decided to give it a few more weeks to see if things would change, but they didn’t. Even after seven weeks, the results were disappointing: this was as flat as flat gets. Our core metrics -- those we value most highly -- didn’t move at all. These include days engaged, the number of people posting, the number of messages, new user retention, etc. In a lot of cases, the job of a Yammer PM is made more difficult when local metrics (metrics that tell us how people use something) go up, but core metrics are either flat or negative. In this case, our overhaul didn’t have any real impact on local metrics either. And that’s very disconcerting because it’s far easier to move local metrics than global metrics.



	
  * The number of people posting images didn’t go up.

	
  * The number of people people posting multiple images didn’t go up.

	
  * The number of posts with multiple images didn’t move. In short, we did not validate our hypothesis. Often when you read blogs about feature overhauls, they are either massive successes or massive failures. But these kind of results are the hardest when it comes to product tradeoffs, analysis, and vision.




## Ship, iterate, or kill it


At the end of the day, we shipped this feature. But it was a difficult and long-debated decision. In the end, it came down to three things:
Without a doubt, we made it easier to attach multiple images.
We believe we created a better experience.
We refactored some very old code. Which actually made it a much easier decision. Even if this were not true, I would imagine that the first two bullet-points would have been compelling enough to base our decision on.

The obvious question is why didn’t this test well? For users, it’s about desire to post a photo rather than ease of posting. I believe our results were flat because people who really wanted or needed to post photos overcame the friction of doing so in the old experience. Making it easier to post photos apparently does not influence someone’s desire to post a photo. For that, we’d have to think about something that is much more top of the funnel. Expecting every feature to address both problems would be unrealistic. Overall, I think this project is a good example of being data-informed and not complete slaves to data.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._



