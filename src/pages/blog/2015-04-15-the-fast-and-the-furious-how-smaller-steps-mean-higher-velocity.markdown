---
author: edithharbaugh
comments: false
date: 2015-04-15 21:11:38+00:00
layout: post
link: https://launchdarkly.com/blog/the-fast-and-the-furious-how-smaller-steps-mean-higher-velocity/
slug: the-fast-and-the-furious-how-smaller-steps-mean-higher-velocity
title: 'The fast and the furious: how smaller steps mean higher velocity'
wordpress_id: 84
categories:
- Continuous Delivery
- DevOps
---

When I first started trail running, Jim Vernon, our running group coach, gave us paradoxical advice to move faster down hills. “Take smaller steps”. If I took smaller steps, wouldn’t I take more time to cover the same ground? However, trail running isn’t like treadmill running or even road running. Trails are full of roots, rocks, steps, logs, and crevices. It’s “the real world” where ankle sprains, knee twists and face plants are very real risks. When descending a steep downhill, with every step your entire body weight is plummeting in free fall, propelled by gravity. With a big step, if you misjudge, you’re more likely to come crashing down. The smaller steps I took, the less force (mass times acceleration) I had landing. And, if a step was wrong, my other foot was close to allow myself to stabilize myself. Now my nickname is “the mountain goat” as I am so quick down hills.

[![downhill](https://blog.launchdarkly.com//wp-content/uploads/2015/09/downhill.png)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/downhill.png)

Best practices in software development like agile, continuous integration, continuous delivery and canary launches are like taking smaller steps to move quicker. If any step is wrong, it’s easy to quickly recover, and more steps allow for more feedback. I recently talked with Javier Soltero and Kevin Henrikson, Acompli co-founders. To make Acompli an app lauded for it’s innovative design, insane utility and blazing speed, they’d taken exactly that iterative, quick-feedback approach. They view their ability to release weekly as key to their success. Acompli checks code in daily throughout the week, uses Bamboo for continuous integration and constantly have internal users (like Javier) using the app. On Monday they’d ship to their beta users (early adopters) who could quickly tell them if features were functional, and more importantly, useful and delightful. Using a a canary launch to the beta users meant there was never longer than 7 days without feedback. In addition, the external users were more thorough than any internal group could ever be. Real users were on the road with patchy wi-fi, low batteries, and bouncing between cell towers. Real users were quick to tell Acompli when they were (or weren’t) on track. Acompli was acquired by Microsoft in December 2014, and is now the default Outlook App, with tens of millions of users worldwide.

Conversely, a developer friend told me about a recent project that his predecessor had worked on for nine months. When the project was released to customers, the project actually dramatically reduced purchases - bad for an e-commerce site that depends on purchases. The developer was ordered to start undoing the feature he’d painstakingly built. The developer quit, upset. Who was the winner in this situation? Not the developer, not the company, and not the customers. Nine months of work had been literally wasted, not even counting the time to recover from the bad feature. In trail running lingo, this project had gone way off in the woods.

With the “aim well, shoot once” approach, all effort had gone into a nine month feature that had not succeeded. In that same time, Acompli had the opportunity to take aim 36 times (9 months x 4 weeks). Taking smaller, quicker steps with continuous integration and canary launches had allowed Acompli to move faster and accomplish more.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
