---
author: jnolen
comments: false
date: 2018-10-19 16:32:07+00:00
layout: post
link: https://launchdarkly.com/blog/moonshots-v/
slug: moonshots-v
title: Moonshots V
wordpress_id: 193437
categories:
- Team &amp; News
tags:
- arduino
- clone flag
- feature flag
- feature management
- hackathon
- moonman
- moonshots
- SDK
- testing SDKs
---









Every quarter LaunchDarkly takes a day out of our regular routine for _Moonshots: _our semi-regular hackathon. It's a chance for everyone to step outside of their daily work, try something new, scratch an itch, get creative—and maybe, just maybe, affect the course of LaunchDarkly's future. That's our Moonshots trophy pictured above, a silver moon man by way of MTV.

The goal of moonshots is to launch something that helps our customers, our teammates, or our service. The rules of moonshots are pretty simple:



 	
  * **Work alone or team up.** Studies show that hack-day teams are more productive and have more fun than solo hackers. Though we never underestimate the power of one, intensely focused developer with a mission to achieve.

 	
  * **Come prepared.** Before the day of Moonshots, every team has to create a _Launch Manifest_ outlining the problem they are trying to solve, the approach they will take, and the outcome they are striving for. No coding or creating is allowed before the starting gun, but design, planning, environment setup, materials gathering, etc. are encouraged.

 	
  * **Show and tell.** Presentations are mandatory. It doesn't need to be fancy, but it's important to share with your team what you attempted and what you accomplished. Even failed projects have valuable lessons for your teammates.

 	
  * **Everyone is encouraged to participate.**  Hack days/weeks-a-thons were born out of engineering culture, but the best ones involve employees from all disciplines.





















It's no exaggeration to say that this edition of Moonshots was the best one we've ever had, the teams created some amazing projects. We were so excited by them that we wanted to share them publicly. You can consider this a sneak preview, because over time, some of these will make their way into LaunchDarkly.


### Clone Flag


Traci Lopez decided to create functionality for cloning flags. She wanted to give users the ability to retain all of a flag's configuration and metadata when cloning. This is useful whenever you have to create similar related flags (perhaps for the same feature), or if you need to change a flag key (which is not allowed by the system). This feature just launched, learn more about it [here](https://launchdarkly.com/blog/launched-clone-flags/).


### [![Clone feature flag in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2018/10/CloneFlags-1024x542.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/CloneFlags.png)




### LaunchDarkly on Arduino


Zurab Davatani and Kevin Brackbill dazzled us with pretty lights. They got the LaunchDarkly SDK running on an Arduino and used feature flags to control some LED light rings. It was an amazing demonstration of just how useful flags can be.

[![LaunchDarkly on Arduino](https://blog.launchdarkly.com/wp-content/uploads/2018/10/Arduino-1024x555.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/Arduino.jpg)


### SDK Test Dashboard


We maintain a lot of SDKs, and all of them have to be tested in many different environments and configurations. While we use CircleCI to do this, it's not easy to navigate and configure hundreds of builds. So Eli Bishop made an SDK build control panel that makes it much easier to do common configurations across many similar build plans. This will undoubtedly save our SDK engineers many hours over the course of the next year.

[![SDK test dashboard](https://blog.launchdarkly.com/wp-content/uploads/2018/10/TestDashboard-1024x590.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/TestDashboard.png)


### A Children's Guide to Feature Flags


Feature flags are a simple but powerful technique, and they should have a powerfully simple explanation. Seth Mazow sketched _A Children's Guide to Feature Flags_, starring everyone's favorite astronaut, Toggle!

[![Toggle the space explorer](https://blog.launchdarkly.com/wp-content/uploads/2018/10/Toggle.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/Toggle.png)





















### And The Winner...Compare Flags


When using feature flags, maintaining separate flag configurations for different environments is essential—LaunchDarkly makes that easy. What isn't easy, however, is comparing flag configurations between two environments or copying those rules from one environment to another. That still requires a lot of manual interaction.

For example, imagine you're preparing to deploy from staging to production. How can you be certain that your flags are configured the same way? Or a second example: we did extensive testing of the new billing pages we recently released, and as we did that, we created and destroyed many different environments for testing. We discovered just how difficult it is to make sure feature flags are exactly in sync across those new environments.

So Zach Davis and Alexis Georges decided to solve the problem by making it possible to compare flags across environments.

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/10/Screen-Shot-2018-10-17-at-12.05.23-AM-1024x544.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/Screen-Shot-2018-10-17-at-12.05.23-AM.png)




















I walked out of the demo room incredibly energized, proud of the team, and excited by what's coming. Stay tuned for future updates about these and other great new features.

We'd love to hear from you about new things you'd like to see in LaunchDarkly, or improvements that would make your workday better. And if you're interesting in joining us for the next Moonshots as part of the LaunchDarkly team, click here and check out our [open spots](https://launchdarkly.com/careers/).








