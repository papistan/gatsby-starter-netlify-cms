---
author: levlaz
comments: false
date: 2018-12-04 21:49:46+00:00
layout: post
link: https://launchdarkly.com/blog/blue-green-feature-flags-combining-operational-and-development-best-practices-to-achieve-progressive-delivery/
slug: blue-green-feature-flags-combining-operational-and-development-best-practices-to-achieve-progressive-delivery
title: 'Blue/Green Feature Flags: Combining Operational and Development Best Practices
  to Achieve Progressive Delivery'
wordpress_id: 193575
categories:
- DevOps
- Feature Management
tags:
- AWS
- blue/green deployments
- feature flags
- re:Invent
- test in production
---

Last week at re:Invent the [AWS team announced](https://aws.amazon.com/about-aws/whats-new/2018/11/the-aws-developer-tools-improve-continuous-delivery-support-for-aws-fargate-and-amazon-ecs/) some great improvements to their continuous delivery offerings for AWS Fargate and Amazon ECS. Notably, you can now [use AWS CodeDeploy to configure blue/green deployments](https://aws.amazon.com/blogs/devops/use-aws-codedeploy-to-implement-blue-green-deployments-for-aws-fargate-and-amazon-ecs/) for these two services. We are excited to see AWS add this functionality as a first class part of their container service offering because it makes it easier than ever for AWS CodeDeploy users to achieve [Progressive Delivery](https://launchdarkly.com/blog/progressive-delivery-a-history-condensed/).

We’ve written about [blue/green deployments](https://launchdarkly.com/blog/powering-blue-green-deployments-with-feature-flags/) as a strategy to enable Progressive Delivery. We’ve also had several talks at our [Test in Production Meetup](https://www.meetup.com/Test-in-Production/), which highlighted blue/green deployments as a way to [test in production without sacrificing availability](https://launchdarkly.com/blog/testing-in-production-without-compromising-availability/).

We talk to a lot of customers about how feature flags can complement blue/green deployments to complete the progressive delivery journey. At first glance these two practices appear to do the same thing, but there are some key differences in these approaches. The way we like to frame the conversation is that a blue/green deployment is an **operational best practice** that allows you to change your infrastructure with the minimum amount of risk. On the other hand, feature flagging is a **development best practice** that allows you to change any part of your application with the minimum amount of risk.

[tweet_box design="default" float="none"]"The blue/green deployment is an **operational best practice** that allows you to change your infrastructure with the minimum amount of risk. Whereas feature flagging is a **development best practice** that allows you to change any part of your application with the minimum amount of risk."[/tweet_box]

Picture this: you just shipped five new features at the end of your two week sprint (great job!). Your operations team leveraged blue/green deployments to deliver the new version of your application out into production safely. At the end of your deployment you noticed that one out of the five features is resulting in a critical bug that causes 500 errors for 90% of all requests. What do you do?

If you only had blue/green deployments, you would roll back to the previous version of your software. This is great because you have quickly recovered from this production incident, but it’s also bad because the other four features you delivered have also been rolled back and now you have to wait an additional two weeks to deliver them back out into production.

With feature flags, you could disable the problematic feature. This allows you to recover from this incident and allow the other four features to provide value to your customers. Everybody wins.

You can see why we feel strongly about combining blue/green deployments with feature flags—it’s a great way to continuously deliver value to your customers with the minimum amount of risk.
