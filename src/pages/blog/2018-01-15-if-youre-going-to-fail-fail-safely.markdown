---
author: heidiw
comments: false
date: 2018-01-15 16:30:45+00:00
layout: post
link: https://launchdarkly.com/blog/if-youre-going-to-fail-fail-safely/
slug: if-youre-going-to-fail-fail-safely
title: If You’re Going to Fail, Fail Safely
wordpress_id: 2173
categories:
- DevOps
tags:
- DevOps
- failure
- feature flags
- harm mitigation
- killswitch
---

Harm mitigation is the flipside of [risk reduction](https://blog.launchdarkly.com/what-makes-a-failure-a-disaster/). Though we want to avoid bad things ever happening and bad choices from being made, we live in a world full of humans, software, and events that require the use of the passive voice. So when something _does_ go wrong, we want to minimize the impact as much as possible.

Seatbelts are the perfect example of harm mitigation. We don’t want anyone to get in a car accident, but if they do, we want them to survive without injury. So we created and mandated seat belts that keep us from flying out of cars, windshields that break into small pellets instead of death spears, and airbags... Our cars have a lot of harm mitigation technology that never gets used until and unless something goes wrong.


### Assume Failure


If you don’t know how your product is going to fail, then you’re missing something. Moreover, because failure modes may have different severity for different people, it’s important you assume all the failure modes you can think of, as well as ask your users what they may experience and how severe those events would be for them. In a SaaS setting, what may seem like a harmless bug around graphics might break business-critical reports...or it might be a feature that the vast majority of your users never access.

For example, the vast majority of social media users may not mind exposing their names and approximate location, but for those who have experienced intimate partner violence or stalking, it could be catastrophic and life-threatening. Be sure you understand the worst cases of failure, not just the common cases, so you can mitigate the most drastic outcomes.


### Fail Safe, Fail Secure


When we [mitigate harm](https://blog.launchdarkly.com/risk-reduction-and-harm-mitigation/), we need to think about what it is we’re trying to protect. For example, nuclear power plants are designed to fail safe. In the absence of positive control and power, they shut themselves down as quickly as possible. On the other hand, time-lock safes are designed to to fail secure. They aren’t designed to have people in them, rather they are designed to protect money, so without a set of conditions including time and codes they will stay locked.

One of the ways that feature flags help everyone fail safely is that there is not a state where a deployment fails in a bad state. If you are always deploying, there is always good code going out, and as it is approved, the new features are turned on. Older styles of deployment could fail in the middle and leave systems in a state neither stable nor updated. CI/CD helps eliminate the disaster of a failed build by making the changes in builds relatively small and pushing the activation of features toward a collaboration between development and business.


### The Kill Switch


Going back to predicting possible states—when you know potential places for failure, you can better understand what transition states can be altered so that when failure happens it hurts less. The easiest path for this in software is the kill switch.

We used to do this process by re-deploying a known good build, but that’s painfully slow when you’re in the middle of an ongoing crisis. Instead, you can always have a transition state of _Hit the kill switch_. If you have a feature marked off in a way that allows you to kill it immediately, you don’t need to redeploy. It’s the SaaS equivalent of a cat falling off a bed but still walking away with great dignity.


### Balancing Act


In our careers, all of us have to balance competing priorities like speed, risk, ease of use, reliability, and planning for the future. We can look at previous large projects at our organizations to show us what kinds of risks were accepted and what were avoided or mitigated. It’s not possible to create anything without making mistakes, but at least we won’t have to switch calendar digits again.

Our best practices include small, rapid iteration, testing in a variety of environments, understanding the business cases we are solving, and listening to everyone on our team as they talk about risks, harm, and avoidance.
