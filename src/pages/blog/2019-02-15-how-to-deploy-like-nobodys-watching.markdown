---
author: az
comments: false
date: 2019-02-15 17:27:36+00:00
layout: post
link: https://launchdarkly.com/blog/how-to-deploy-like-nobodys-watching/
slug: how-to-deploy-like-nobodys-watching
title: How to Deploy Like Nobody’s Watching
wordpress_id: 193721
categories:
- Continuous Delivery
- DevOps
tags:
- canary launch
- continuous delivery
- dark launch
- DevOps
- feature flag
- feature management
- microservices
---

_Originally published on [The New Stack](https://thenewstack.io/how-to-deploy-like-nobodys-watching/) on January 18th, 2019._

There is a continuous desire in DevOps to have a greater connection between the development of a service or application and the operation of the code in production. Because of this, we’ve seen new tools and methodologies around software development emerge. And this is of great interest to product managers (PMs), such as myself, who are always looking for new ways to help our teams be more successful.

But unfortunately, if you’ve done enough product launches, you’ve no doubt experienced a “simple” feature update that turned into [a total disaster](https://launchdarkly.com/blog/the-penny-glitch-that-cost-big/) that took you all night (or even days) to fix. Like every other PM, I’ve dealt with more than my fair share of flubbed launches. Over the years I have looked for ways to better prepare and support my teams, as well as limit the impact of mistakes on my users.

One key concept that has proven valuable is the acknowledgment that the deployment of code does not have to be the same as the release of a new feature — there can be a deliberate separation. When done well, this allows engineers to develop code faster and greatly reduce the risk for the business that is often associated with this increased release velocity.

Today, when my team begins working on a new feature, we allow developers to [start deploying to a staging environment immediately](https://launchdarkly.com/blog/continuous-incrementalprogressive-delivery-pick-three/), even before the code is complete. As soon as the code is complete, we’ll start deploying to production to start our testing. (Yes, we test in production, as we have yet to find a good way to replicate the internet in an isolated environment.) Once the feature is stable and functioning as designed, I can own the release of the feature without needing to involve the development team. This allows the developers to move on to the next project, while I release the features on a timeline that makes sense for the business. The best part is that even if things don’t go quite as planned, I have the ability to kill the release with the flip of a switch.

This idea of “dark” or “canary” launching also makes it possible to test out non-technical problems. If early users don’t engage with our updated features, or if fewer new users convert on new workflows, then we can simply turn off the feature without having to make any code changes or even having to re-deploy and move on to our next brilliant idea.


### Keeping Up With the Microservices


In the world of packaged software, there was a strong justification for creating a single monolithic application. This supported the long development cycles and tightly coupled timelines. As release cycles have become shorter and shorter there has been a need to break up these monoliths into smaller services that are easier to update independently. This ability for independent updates is intended to allow teams to move more quickly.

Even in the world of monolithic applications, engineers would use feature flags to hide or control access to features and functionality. Feature flags are essentially an if-then statement that can be changed without having to re-deploy an application. The earliest version of feature flags was stored in -config files (sometimes with hidden variables) and were viewed as “advanced” configuration options.

When I was at VMware, we used these to explicitly enable features for specific customers. This could have been for a driver that was not generally supported or for an integration that was not available to everyone. The support organization would enable the feature flag, and the customer would have the feature they needed. This allowed flexibility to release certain features without having to support every customer and every environment.

When microservices came along, the challenges shifted. Development teams started pulling apart large monolithic applications into component services. Microservices have made it much easier to update these smaller components independently of each other. But this independent delivery of services has also shed light on the tight coupling that often persists after services are separated. Successful teams thus look to feature flags as a way to maintain deployment velocity while [avoiding failure due to compatibility issues](https://launchdarkly.com/blog/designing-for-failure-to-avoid-disaster/) across services.

With feature flags, teams can deploy and release new versions of a service with certain flags disabled until the needed updates were present in dependent, or linked, services. This approach has strengthened the value of a [closer relationship between developers and operators](https://www.youtube.com/watch?v=LdOe18KhtT4). Developers put the controls in place and Operations have control of the behavior of an application or service post-deployment.

Suddenly, the idea of a “launch” has much greater flexibility. Operations teams “dark launch” features using feature flags and targeting rules to explicitly choose users and cohorts to expose to new functionality or behavior. When I was at GitHub, we used feature flags to do these dark launches of new and updated features. We pushed updates onto our production servers and then selected cohorts, or specific users, who would get early access to new features before the entire population.


### Launch Is Not Binary, It’s a Spectrum


Dark launches, canary launches, the desire for more gradual release progression and control over user exposure is driving a greater need for robust Feature Management.

Enterprises are also being confronted with an increasing number of use cases that require the delivery of a personalized application experience. Kids these days, for example, always want the latest and greatest, while my folks curse at their phone if the shape or color of a button changes.

Building your code with control points allows the business owner to have greater flexibility to release new functionality at the pace that is appropriate for their users — even when their users need to move at different paces. Conveniently, the same control points can be used to test in production and create a better experience for both early adopters and stability hold-outs.

There has always been the question of “new features or stability?” — But why not both? Implementing Feature Management in your development lifecycle allows developers and operators the certainty of testing and validating in production without risk to end users. The more progressive launch phase allows PMs, or business owners, to have much more control in how an application or service is experienced by a customer. It gives PMs a way to take some pressure off of engineers and [own the release of features](https://launchdarkly.com/blog/progressive-delivery-a-history-condensed/) at a rate users are comfortable with, and make available only the features a user requires.
