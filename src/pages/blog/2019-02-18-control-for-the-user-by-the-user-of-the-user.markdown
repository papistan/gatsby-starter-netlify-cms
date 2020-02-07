---
author: az
comments: false
date: 2019-02-18 16:34:10+00:00
layout: post
link: https://launchdarkly.com/blog/control-for-the-user-by-the-user-of-the-user/
slug: control-for-the-user-by-the-user-of-the-user
title: 'Control: For the User, by the User, of the User'
wordpress_id: 193726
categories:
- Continuous Delivery
- DevOps
tags:
- continuous delivery
- DevOps
- feature flag
- feature management
- SDLC
- technical debt
---

_Originally published on [The New Stack](https://thenewstack.io/control-for-the-user-by-the-user-of-the-user/) on January 30th, 2019._

Feature Management creates a new kind of feedback loop for product development. We can see how the changes we make affect user behavior and business results. We can analyze behavior data to get a better sense of what works for users, and what doesn’t. Ultimately this gives us more confidence in the decisions we make as we build our products and lend a better likelihood that they will be successful.


### Getting and Using Data


Many companies have adopted tools for monitoring infrastructure and application performance. Things like application performance management, log analysis and distributed tracing are great for identifying changes that will improve the performance of the application infrastructure. However, it’s not easy for product managers (PMs) to use these tools to relate feature changes to actual user or business metrics. Since a PM would have to put in an Operations request for every new metric, it’s probably not going to happen very often unless they’ve made good friends in the Ops team.

Now if a company has adopted tools for managing the release of functionality with feature flags, then why not use this same tooling to measure the use of those flags and correlate usage to ops and business metrics? As mentioned in the preceding articles in this series [“](https://thenewstack.io/continuous-development-times-are-a-changin/)[Continuous Development: ‘Times Are a-Changin’”](https://launchdarkly.com/blog/continuous-development-times-are-a-changin/)  and [“How to Deploy Like Nobody’s Watching](https://launchdarkly.com/blog/how-to-deploy-like-nobodys-watching/)[,](https://thenewstack.io/how-to-deploy-like-nobodys-watching/)” developers are using feature flags as a best practice to reduce risk in development cycles by separating code deployments from feature releases. Since these control points are already in place, this is a great opportunity to use those feature flags as counters to track user interaction with given sections of code. This means you can create a model for user interaction with your application that can be quantified, leading to more data-driven decisions for your product.

Using controlled releases of features in the context of experiments is an effective method for collecting user behavior data. Exposing a segment or percentage of users to a new or improved feature and measuring the outcomes based on business metrics such as conversion, increase usage, or even dollars, can lead to data-driven development of your application.

When engaging in hypothesis-driven development there are times you want a large, completely random population for your experiment. However, those of us who have built products for B2B companies know that this can easily result in disaster. For this reason, it is important to have a system that can be flexible in dictating users as well as explicitly supporting the ability to opt-out specific users or cohorts. In some cases it’s a good idea to identify the happiest users first, you can even link this to a Net Promoter Score (NPS). These users are more likely to be excited about new features and give honest feedback. They are also less likely to start an angry tweet storm if they find the new feature confusing.


### Smaller Changes = Faster Recovery from Mistakes




<blockquote>_“Every feature I have ever launched has been immediately adopted and loved by all users,” _said no product manager ever.</blockquote>


Launching new things without data and feedback can be stressful and scary. For older methods of software delivery, this risk is exacerbated due to longer dev cycles and bigger releases. If something does not meet the need of the customer, not only do you have a disappointed customer, but your developers are frustrated and discouraged because they just spent a significant amount of time building something that won’t be used. In my experience, this is also a guaranteed way to destroy the trust between development and product management.

In many ways Product Management is like Meteorology — you’re making predictions based on data. Continuous Delivery is the idea of moving from monthly forecasting to hourly. Measuring the reaction to small changes gives you, the predictor of customer temperature, the ability to adjust your product delivery with much greater accuracy.

If all of our hypotheses either meet intended outcomes, do nothing or end up frustrating customers— how do you maximize the time and effort spent on the work that delights our customers? It’s hard to tell up front because some of our best ideas don’t live up to our customers’ expectations. But if we can keep the increments of change small, leverage the data from experiments where our hypotheses fail, and iterate quickly, we are far more likely to continue down the path of increased customer engagement.


### Do Your Feature Flags Spark Joy?


At this point your developers are moving fast, you’re delighting customers, and your operations team has amazing control without having to re-deploy code — but don’t forget to clean-up. As you’ve been creating this optimized software delivery pipeline, your developers have been creating a lot of code that was intended to be transitional. They created an experiment. There was a code path that was a clear winner. 100% or your users have been using the winning variation for months. Now, it’s time to remove the unused code.


<blockquote>_“The only good diff, is a red diff.”_ – Charity Majors</blockquote>


When code starts looking like our refrigerators, with dubious “food” and literal science experiments, it’s time to clean it up. Another best practice to adopt with feature management is the idea of code expiration. Establishing a process is great — some teams will even create a “clean-up” PR at that same time as a merge PR to remind them of the work that needs to be done.



Going back to our feature management platform as a source of truth for clean-up can also be very useful. It takes the guesswork out of knowing if a feature flag is still being used if the system can track the date and time of each user calling the flag. And because of the wrapper-like nature of feature flags, it’s easier to isolate and remove these expired code segments.

Feature management is not just about using feature flags to streamline releases. It is the tooling that brings business metrics into the Continuous Delivery model and complements the DevOps methodology of measurable outcomes. This allows us to make adjustments to the release of product features with greater confidence and help our developers spend their time building cool new stuff instead of wading through moldy technical debt.
