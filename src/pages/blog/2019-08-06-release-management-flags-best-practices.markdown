---
author: dparzych
comments: false
date: 2019-08-06 16:28:18+00:00
layout: post
link: https://launchdarkly.com/blog/release-management-flags-best-practices/
slug: release-management-flags-best-practices
title: Release Management Flags Best Practices
wordpress_id: 194127
categories:
- General
tags:
- best practices
- release management
---

When most people think of a feature flag, they probably think of a flag that controls who can see a feature, when. Release management is one of the most common use cases for feature flags.


## Release Management Flags Use Cases


Whether you call it early access, a canary release, or a beta, giving a select group of users access to features prior to release helps you fine-tune a feature before you release it to everyone. Starting small and rolling out to larger groups over time helps you:



 	
  * Observe the behavior of the systems and services under increasing load.

 	
  * Collect user feedback and make changes if you need to.

 	
  * Limit the blast radius if something goes wrong.


A release management flag is intentionally short-lived. Once 100% of users have access to the feature, remove the flag.


## Deploying Release Management Flags


The two most common deployment models to use are ring deployments and percentage-based deployments.


### Ring Deployment


Jez Humble introduced the concept of a ring deployment in his book [Continuous Delivery](https://www.amazon.com/dp/0321601912?tag=contindelive-20). Different groups gradually receive the feature to manage the risk of deployment. Select users for each group based on a set of similar attributes or an opt-in process. Then, make features available to the selected groups. For example, release to internal users first, and then beta users, and then to all users.


### [![Three concentric circles showing internal, beta, and all users.](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Ring-Deployment_image-300x300.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Ring-Deployment_image.png)




### Percentage Deployment


Selection of who receives a new feature occurs randomly in a percentage-based deployment. The new feature rolls out to 10% of users, then 25%, then 50%, until all users receive the new feature. These deployments are useful when you cannot run a beta program, or there is little variation in your targeted user base. If you run a small B2B application with the same 1,000 monthly active users each, a percentage-based deployment

Some companies automate percentage-based rollouts gradually increasing the number of users receiving the new feature. Too many errors, or a response time exceeding a set threshold results in the termination of the rollout.

You can combine ring and percentage-based deployments. You first deploy with selected groups and then use a percentage-based deployment to roll out to the remainder of your user base.


## Release Management Flags Best Practices


Creating release management flags is a three-part process. First comes the planning, then the implementation, and finally the deployment. Consider the following best practices for each phase in the process.


### Planning


Before you code or deploy your first feature flag, follow these steps to set yourself up for success.


#### Make Feature Flags a Priority from the Start


The right time to think about whether a feature needs a flag is during the design process. The design of a feature may vary based on whether or not it is behind a flag. When feature flags are an afterthought, you end up with flags that don’t work as expected, don’t target the right users, or that have unexpected behaviors. Thinking about a feature flag during the design phase requires you to think about who will use the feature. If during the design phase, you determine the feature is for larger enterprises, you know the flag should target large enterprises. Targeting customers at small or mid-sized businesses would not be appropriate.


#### Understand the Purpose of a Flag


A flag can serve many purposes. Release flags can control how a feature rolls out to users as well as to serve as a kill-switch if something goes wrong. If a flag will serve multiple purposes, notify all parties and make sure everybody has access to the flag.


#### Establish Naming Conventions


In our [short-term and permanent flags best practices](https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/) blog, we discussed the importance of coming up with a naming convention before configuring your first feature flag. A consistent naming strategy ensures everybody understands the purpose of the flag and helps to avoid technical debt.


### Implementation


You’ve planned the feature; now you’re ready to implement the flag. Consider the following:


#### Understand the Deployment Path


Before you release a feature, it is common to do a beta release or canary launch. These both allow a select group of users to test out a new feature and provide feedback. Not all features follow this path to production. Some features release to all users at once while some will do a percentage-based roll-out. There is not a right or wrong answer when it comes to how you deploy, but to create an appropriate flag, you need to have a deployment plan in place.

Questions to ask to understand the deployment path:



 	
  * Do features get deployed to staging, pre-production, or test environments before rolling out to production?

 	
  * How will you roll out the feature to users?

 	
  * Is it first used by developers, then internal staff, then external users?

 	
  * Will there be a beta or a canary launch?

 	
  * Will release occur through a controlled rollout or to all users at once?




#### Test the Behavior of the Flag


We are big proponents of testing in production. However, this does not mean you only test in production before you deploy a flag, you should test the behavior of the application with the flag toggled on and off. This is especially important if the feature is related to a schema or database change. What happens when a feature is on and then toggled off? Is data lost? Is data corrupted?

Another aspect of testing is dogfooding (using your own product or service internally). This lets you test out changes on internal employees first. Put yourself in your customer's shoes. With dogfood environments, you can see firsthand the pains users might experience with a feature. Using the application as a user would is a step towards [empathy-driven development](https://firstround.com/review/empathy-driven-development-how-engineers-can-tap-into-this-critical-skill/).

You can test all you want before deployment, but until customers use the feature in production, you won’t know if it is working and what needs to be changed. This is why we regularly endorse testing in production.


#### Configure a Fallback Value


What happens with a flag if a user is not able to access the most recent settings? What happens if a user accesses your application in offline mode? Configuring a fallback value can eliminate unexpected experiences or errors with interrupted connections. Every flag should have a fallback value describing the expected behavior of the feature in case failures occur during evaluation. Should the flag be on or off by default?


#### Keep Features Small, But Not Too Small


Not every feature needs a flag, and sometimes a feature needs multiple flags. You don't need to wrap a tiny change in a feature flag unless you're very concerned about its impact to users. Large features such as a new dashboard might require multiple flags.


#### Create Segments or Cohorts


Before you deploy, you need to determine how to segment your users. Identify what attributes determine who sees a feature when.


### Deploying


You’ve planned and implemented the flag, all that is left is to cross your fingers and deploy to production. Wait, not so fast. As you deploy, consider the following:


#### Track Metrics


Metrics help us determine whether something is improving or degrading. What metrics do you need to track regarding features? Availability, reliability, and response time of an application should not change with the deployment of a new feature. Set up monitoring to track performance before, during, and after you deploy code to ensure performance does not get worse. Tracking metrics such as page load time, errors, uptime, conversions, or user registrations can tell you whether a feature is performing well or causing problems.

The metrics you track will vary based on your business and objectives.


#### Avoid Technical Debt


Release management flags should be short-term. This means you should remove a flag after it has rolled out to 100% of users. Technical debt accumulates when you forget to remove a flag from the code. Put processes and reminders in place to remove the flag. We highlighted some creative ways to do this in our[ short-term and permanent best practices](https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/) blog.

Looking for more best practices? Check out the other blogs in the series:



 	
  * [Long-term and short-term flags best practices ](https://launchdarkly.com/blog/best-practices-short-term-permanent-flags/)

 	
  * [Operational flags best practices ](https://launchdarkly.com/blog/operational-flags-best-practices/)


Coming soon:

 	
  * Experimentation flags best practices

 	
  * Entitlement flags best practices


