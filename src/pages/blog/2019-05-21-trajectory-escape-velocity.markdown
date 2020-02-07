---
author: dparzych
comments: false
date: 2019-05-21 19:01:00+00:00
layout: post
link: https://launchdarkly.com/blog/trajectory-escape-velocity/
slug: trajectory-escape-velocity
title: 'Trajectory: Reaching Escape Velocity'
wordpress_id: 193897
categories:
- Continuous Delivery
- DevOps
tags:
- bia
- chaos engineering
- experimentation
- process
- test in production
- Trajectory
---

About a year ago I heard a talk from Tamsen Webster on “[The Red Thread](https://www.youtube.com/watch?v=SRsPo3rfv94).” This concept discusses how as humans we look to make meaning from what we see. This search for meaning happens unconsciously and is influenced by who we are—our thoughts, beliefs, and biases influence how we create meaning.

At conferences, speakers will present to audiences of tens, hundreds, or thousands of people—and every person there will extract different meanings from the talk. Often, I find similar themes and concepts among the many talks given at a single conference. I know part of this is by design and part of this comes from the schema I am using to create meaning of what I am hearing.

LaunchDarkly recently held their first ever conference, [Trajectory](https://www.trajectoryconf.com/). As this was five days after I started, attending was a great way for me to learn more about the company, our products, and customers. Below is my take and learnings from attending Trajectory.


### Testing in Production


Being fairly new, I was looking to learn as much as possible about testing in production. The talks from [Ramin Keene](https://twitter.com/rmn) and [Jason Yee](https://twitter.com/gitbisect) provided what I was looking for. People often get anxious when testing in production is discussed. “You can’t release code without testing!” Testing in production does not mean you release without testing. Rather, testing in production allows you to test in a more real environment before code is released, and it is the only place you can verify if systems are working as intended. Two aspects of testing in production are experimentation and chaos engineering.

Ramin talked about the differences between experimentation and testing. Testing is about verifying, confirming, and integrating code. There is a known good state and tests are run to make sure you get the expected response/answer. Experimentation, on the other hand, leads to new knowledge. It is about discovering the unexpected and learning how systems react to different inputs and changes.

Chaos engineering, which was covered in Jason’s talk, is a type of experimentation as you are creating a learning environment. You are testing what will happen to the systems under certain failure conditions. You can have a hypothesis about what you think will happen but systems don’t always behave the way we think they will.

Testing in production and experimenting may be scary, but if you go into it with an open mind and a philosophy to celebrate the learnings (and have fun), it may become a little less scary. Part of making it less scary is having a defined process around what the experiment or game-day will look like.


### Processes


I’m a big fan of process. A well-defined process helps people know what their responsibilities are, what to expect, and what constitutes success. Sometimes you need to be spontaneous and circumvent the process, but always running that way will not lead to success. [Hiten Shah ](https://twitter.com/hnshah)recently wrote about this in his blog “[My Billion Dollar Mistake](https://producthabits.com/my-billion-dollar-mistake/).” Given my love of process, I enjoyed hearing and learning about the processes people had implemented.

All three keynote speakers mentioned or discussed process. [Cindy Alvarez](https://twitter.com/cindyalvarez) outlined a process to frame conversations. One of the biggest take-aways I got from the conference was her process of asking people on a weekly basis what they are worried about. This helps to curtail issues before they become too big of a problem. If you aren’t asking people directly, then you have no way of knowing.

Processes should not be carved in stone. They should be fluid and be changed when the need arises. [Adrian Cockcroft](https://twitter.com/adrianco) cautioned against avoiding complex one-size fits all processes. A process that worked at one company or for one team may not work everywhere. Processes also need to be examined to see if they need updating.

During her breakout session, [Emma Humphries](https://twitter.com/triagegirl) talked about how Mozilla upholds its values and keeps up with change. This includes identifying when there are biases in the processes and updating them to be more inclusive. When a process for prioritizing features is held on-line via votes it meant only those people that knew where to find the discussion and had time could participate. The process for prioritizing features was changed at Mozilla to make it more inclusive and remove bias.


### Bias


The topic of bias came up in more than just Emma’s talk. This is another subject that is near and dear to my heart. I’ve previously [written](https://sdtimes.com/devops/site-reliability-engineer-dont-fall-victim-to-the-bias-blind-spot/) and [given talks](https://www.youtube.com/watch?v=8rOHb2yoSw4) about bias. The more people talk about bias the more aware we become of how these biases influence our thoughts and behaviors.

Cindy talked about authority bias. Authority bias is our tendency to follow the instructions of an authority figure even if we disagree with them. As our stress levels increase or we are tired authority bias kicks-in to a greater degree.

When our processes, brains and biases get in the way of making good software it is time to take a step back and see what needs to change. Do processes need to be put in place or changed, do you need time off, do you need to run the idea by somebody else?

The talks and presentations given at Trajectory are now available—[check them out here](https://launchdarkly.com/trajectory-signup/). And if you like what you see, make sure you [join us in 2020](https://www.trajectoryconf.com/).
