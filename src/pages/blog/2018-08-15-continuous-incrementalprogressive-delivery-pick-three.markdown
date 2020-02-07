---
author: johnkodumal
comments: false
date: 2018-08-15 19:05:28+00:00
layout: post
link: https://launchdarkly.com/blog/continuous-incrementalprogressive-delivery-pick-three/
slug: continuous-incrementalprogressive-delivery-pick-three
title: Continuous, Incremental, Progressive Delivery—Pick Three
wordpress_id: 193268
categories:
- Continuous Delivery
- DevOps
tags:
- Agile
- CD
- CI
- continuous delivery
- DevOps
- incremental delivery
- progressive delivery
- SDLC
---

Software developers have spent the last decade talking about Continuous Delivery and the benefits of delivering working code as often as possible. But it turns out that's only one part of the whole picture of software delivery. Modern teams actually have three distinct outcomes they are trying to achieve—a holy trinity of _continuous_, _incremental_, and _progressive_ delivery. Each of these delivery practices can help your team move faster with less risk.


### Continuous Delivery


_[Continuous Delivery](https://continuousdelivery.com/)_ is a set of practices that ensure your code is always in a deployable state. You accomplish this by increasing the frequency at which code is committed, built, tested, and deployed—steps that in the past only occurred at the end of a project when it was ‘code complete’.

Because your team is delivering frequently, every change is smaller. Changes are more isolated and less risky. Problems are identified more readily, and bugs are fixed more easily because they are discovered immediately.

The tools required to achieve Continuous Delivery include distributed version control (Git or Mercurial), continuous integration (CircleCI, Travis, or Jenkins), code review and source hosting (Gerritt, VSTS, or GitHub), and more. Continuous Delivery also requires a cultural shift for engineers to work more collaboratively and openly.


### Incremental Delivery


If you are practicing Continuous Delivery, you can release at any time. Doing so reduces engineering risk, and you can use this super-power to create better products.

_Incremental Delivery_ is the art of breaking large projects into smallest possible units, which you release to your customers as soon as they are complete. By releasing each small increment of value, you get customer feedback at the earliest possible moment. This lets you optimize for learning, so you can orient and adjust course early in each new feature.

Incremental Delivery doesn’t necessarily involve or require new tools. Instead it requires its own cultural change in project planning and discipline.



 	
  * **Planning.** Find ways to decompose new features into incremental shipments that provide coherent bits of customer value. Optimize your schedule around what is most uncertain. Consider what you need to learn most urgently. Failing to plan this way means lengthening your feedback cycles and delaying the time before a customer experiences the value of your dev work.

 	
  * **Feedback. **Do you know what you are trying to achieve? Are you measuring how your new feature works once delivered? You must gather that feedback and _act_ on it. Adjust your plans, clarify your UX, or even abandon the project if it's not achieving your goal.

 	
  * **Discipline.** After most of the customer value has been shipped, do you have the discipline to follow through and create a _lovable_ product? This is the difference between a slapdash product that checks off feature boxes but isn’t great to use, and a polished product that anticipates a user’s needs and is a _pleasure_ to use. Learning from real users is the surest way to get there.




### Progressive Delivery


_Progressive Delivery_ is the technique of delivering changes first to small, low risk audiences, and then expanding to larger and riskier audiences, validating the results as you go.

Progressive Delivery comes in two complementary flavors: environments and user. You can deliver progressively to environments using canary builds or blue-green deployments to limit exposure when new code is deployed. Progressive Delivery for users, on the other hand, lets you limit the exposure of which users see a new change. Whether it's internal testers, or beta users, or percentage-based rollouts—making changes progressively helps you move forward with confidence. That's what Feature Management tools (like LaunchDarkly) specialize in.

Progressive Delivery is a transformative cultural shift that will help your team spend more time creating value and less time managing risk.


### Three Practices, Built for Speed


These three practices are distinct from each other and they each address a different challenge in the software development process:



 	
  * **Continuous Delivery** helps your team move faster by making each change small and manageable.

 	
  * **Incremental Delivery** helps your team move faster by increasing your opportunities to learn and adjust.

 	
  * **Progressive Delivery** helps your team move faster by reducing the risk of each change by controlling the audience exposed.


The holy grail, of course, is achieving all three of these on your team. At LaunchDarkly our goal is to help teams achieve this. [Progressive Delivery](https://launchdarkly.com/blog/progressive-delivery-a-history-condensed/) is our jam. It’s what we preach—the ability to de-couple deployment of software from releases of features. All three practices reinforce and enhance each other. And we've seen firsthand how achieving this holy grail can transform a software team.

Ask us how!
