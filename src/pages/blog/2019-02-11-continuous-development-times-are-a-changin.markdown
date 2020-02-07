---
author: az
comments: false
date: 2019-02-11 21:02:17+00:00
layout: post
link: https://launchdarkly.com/blog/continuous-development-times-are-a-changin/
slug: continuous-development-times-are-a-changin
title: 'Continuous Development: ‘Times Are a-Changin’'
wordpress_id: 193717
categories:
- Continuous Delivery
- DevOps
tags:
- continuous delivery
- DevOps
- SDLC
- waterfall
---

_Originally published on [The New Stack](https://thenewstack.io/continuous-development-times-are-a-changin/) on January 7th, 2019. _

Recently, the rate at which updates are released has become lightning-fast. When I first started doing product development at EMC and then later at VMware, we used development frameworks like “[waterfall](https://en.wikipedia.org/wiki/Waterfall_model)” to release new features every couple of years. Sometimes, we would measure releases in months the same way parents refer to their 22-month-old toddler. At times, even this was too fast for our enterprise clients since they needed to update training videos and business processes with each new feature.

In 2014, I left VMware for GitHub, and I was in awe of how they sometimes released multiple updates per day using practices like automated testing and continuous integration, short-lived branching, and continuous deployment. This new pace reflected a shift in the way people and businesses were thinking about and adopting software. Instead of being confined to regimented processes, employees were empowered to “ship” early and often, and iterate quickly.

Today, businesses are racing to keep up with the Lyfts and Netflixes of their industries. Looking to the future, in five to seven years there will be an influx of employees who have grown up in a world where the iPhone has always existed and the internet is always on. All work tasks will be approached from the perspective of, “There’s an app for that.”


<blockquote>Not only are companies increasing their release velocity, they are also experiencing external expectations from users for more innovative services.</blockquote>


As I’ve seen these changes take place over the last few years, I’ve been trying to make sense of what the faster pace of software means for product managers. Not only are companies increasing their release velocity, but they are also experiencing external expectations from users for more innovative services. It’s tricky to balance these two sides, but if we think about the incremental development of features in three distinct phases — concept, launch and control — then it’s easier to create a strategy for your product/platform that will keep up with urgent expectations without sacrificing quality and user experience.


### Start with the End in Mind


The concept phase includes identifying what implications a new feature will have on overall service. There are two high-level buckets that any feature development falls into — updates to existing features and workflows and net-new functionality.

For updates or iterations on existing features, the approach of [hypothesis-driven development](https://blog.launchdarkly.com/hypothesis-driven-development-for-software-engineers/) is ideal for measuring success and iterating quickly. In the case of net-new functionality, there is a benefit to identifying these types of efforts during the Concept phase to create appropriate management options for the Control phase of the feature lifecycle. Product managers must work closely with stakeholders involved in design, marketing, technology, business and sales from the get-go.


### Create a Continuous Experiment


Another key part of the concept phase is to remember that many of our “great” ideas don’t actually add much to the customer experience. And as attached as we can be to certain ideas, ultimately what we’re creating is for our users.

It becomes easier to detach ourselves from failed brainchildren if we think of new releases as experiments where we can hypothesize about the value we expect a new feature to deliver. When we test them out we should measure the impact we’re having on our users. This could include:



 	
  * Greater customer satisfaction;

 	
  * Reduced churn;

 	
  * Higher conversion;

 	
  * Fewer support calls;

 	
  * Longer engagement.


By framing releases in this way, product managers can swing the focus of a launch from the software itself to the effects it will have on the end-user, and what tweaks need to be made to the software to maximize positive results.


### It’s All About Control Points


We all make mistakes. Ideally, in the case of our product decisions we can limit the impact of those mistakes and have data that enables us not to make the same mistakes again. One of my brilliant ideas might fall short of customer needs or expectations, or worse, break something that some of those customers relied on.

When (not if) this type of mistake occurs, how do you minimize the impact and reduce the time to resolve this negative impact? If we think back to the packaged software days this could be terribly painful. This is why in waterfall development there was such a focus on QA, use cases, and long cycles.

In the SaaS world, we have made vast improvements with Agile and Scrum methodologies, but how long is an acceptable resolution time? If your resolution process requires a full sprint, you’re in a rough spot. Even for teams that have a prioritized remediation process, you’re still likely bound by the time it takes for you to re-deploy the responsible service or application. And that assumes that roll-back is an option and doesn’t include any development or validation if new code is required.

The primary goal for teams moving to a Continuous Delivery development model is agility. The often quoted Facebook mantra, “Move fast and break things,” leaves off the greatest priority for enterprise companies: “But with less risk.”

What if your ability to resolve a bad release was as easy a flipping a switch? Or better yet, what if you could control who sees what features and when? This is how Netflix, Google, Facebook, and others who deliver software with this model are successful. They have recognized the need to separate the ‘deployment’ of code from the “release” of features. They have done this through the use of control points that exist in the application/service that are accessible after deployment.

On the other hand, a new feature might provide such tremendous value that customers are willing to pay more for it. In that case, we could think about implementing control points to place features into different tiers of a service without having to deploy different instances of the service or maintain different code paths for different offerings. Instead, the feature availability is adjustable without having to change the code, you just change the setting at the appropriate control point.

We need to build the capabilities to support either scenario into the code from the beginning. By looking at the expected life cycle of a feature, we can figure out where control points (or “feature flags”) should be configured, whether they should be transient or permanent, and even whether they’ll need to evolve. In some cases, a transitory control point makes it easier to turn an experiment on/off for experimentation with certain users, while a permanent control point might be better for operational control or customizing feature combinations for different kinds of users or pricing tiers.


### What Comes Next?


Tooling and best practices in DevOps are changing. By developing better processes and using feature-management tools, we can put ourselves in a position to consider more options up front.

But what comes next? After moving through the concept phase, we get to launch and control. In the next two posts I’ll write more about how the launch phase requires implementing mechanisms to separate technical deployment from product release. I’ll also cover how the control phase requires implementing mechanisms for easily adjusting product features after launch.
