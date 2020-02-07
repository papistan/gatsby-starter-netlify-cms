---
author: justinucd
comments: false
date: 2017-04-07 16:26:23+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flag-transition-setup-guide/
slug: feature-flag-transition-setup-guide
title: Feature Flag Transition & Setup Guide
wordpress_id: 1503
categories:
- Feature Management
tags:
- configuration
- feature flags
- LaunchDarkly
- management
- setup
- transition
---

### _A step-by-step guide for integrating LaunchDarkly into your app and adopting feature flagging best practices_


You’re now at a decision point. You want to buy a feature flagging management solution, but you are not sure how difficult the switch might be. You either have an existing system in place or you’ve never tried feature flagging before.

The transition process is actually not as daunting as you think. In fact, it’s an opportunity to clean up technical debt, mitigate risk, and start deploying better software, faster. From start to finish, this guide will walk you through the process of successfully integrating LaunchDarkly into your development process.


#### 1. New Team Member Orientation





 	
  * Use the QuickStart tutorial.  Create a feature flag for the platform of your choice using the step-by-step tutorial. We provide well-documented SDKs for Java, JavaScript, PHP, Python, Go, Node.JS, .NET, Ruby, Python Twisted, iOS, and Android.



 	
  * Install LaunchDarkly in a test app.  In the QuickStart section, select “Install an SDK”.  Use this guide to install a simple feature flag in the test app of your choice. LaunchDarkly provides “hello-world” test apps to help you get familiar.



 	
  * Check out our [documentation](http://docs.launchdarkly.com). It’s important to understand the LaunchDarkly fundamentals.  In LaunchDarkly, feature flags are evaluated in-memory using one of our SDKs. Our user interface (app.launchdarkly.com) lets you create feature flags and targeting rules that are streamed to our SDKs in real-time.  You pass user objects to our SDKs, which evaluate the appropriate flag values for those users in microseconds. These feature flag events are sent asynchronously to LaunchDarkly, allowing you to easily manage users via our dashboard.



 	
  * Start targeting users and playing with percentage rollouts.  Go to your feature flag dashboard and select a feature flag ([docs](http://docs.launchdarkly.com/docs/targeting-users)).

 	
    * On the targeting tab, you can:

 	
    * Target individual users

 	
    * Create custom targeting rules

 	
    * Manage percentage rollouts

 	
    * Set a default rule

 	
    * Set an off variation






 	
  * Create a [multivariate flag](https://blog.launchdarkly.com/launched-multivariate-feature-flags/). LaunchDarkly can do more than just evaluate true and false feature flags. Create multivariate flags that have multiple flag variations. These variations can be strings, numbers, and JSON arrays/objects.




#### 2. Select a coordinator and document the transition


Your coordinator will take ownership of the transition process.



 	
  * This coordinator should be familiar with [feature flagging best practices](http://featureflags.io/feature-flags-best-practices/?utm_source=launchdarkly_blog&utm_medium=organic) and serve as the primary contact between your organization and LaunchDarkly.

 	
  * Construct a document and/or use your issue tracker to itemize the switch. This is an opportunity to implement best practices in your development and release process.




#### 3. Separate feature flags from configuration values


Scan your application and identify your feature flags.



 	
  * It’s important to understand what a feature flag is, and what it isn’t.

 	
  * The primary purpose of a feature flag is to control access to a feature based on the context of a user. On the other hand, a configuration value is primarily used to configure a permanent parameter, irrespective of a user’s context.

 	
  * Feature flag use cases

 	
    * Roll out a new checkout flow to 1%, 10%, and 100% of your users

 	
    * Toggle a new beta feature for your beta testers

 	
    * Sunset a poorly performing feature

 	
    * Manage a long-term state, like maintenance mode or subscription plans

 	
    * Serve a new upgrade to users who live in Canada and have an Android phone




 	
  * Configuration value use cases

 	
    * Set the hostname for your application server

 	
    * Set authentication credentials and settings for services and backend stores

 	
    * Set static rate limits for your application service

 	
    * Set a directory path for data storage







#### 4. Clean up technical debt by removing old flags


Remove the feature flags you don’t want anymore



 	
  * This process is an opportunity to mitigate technical debt and remove all of the clutter from the past. LaunchDarkly has flag statuses that indicate when you particular feature flags are safe for removal.




#### 5. Identify components that you would like to flag


Now that feature flagging will be easy, you should identify components of your application or particular processes that you would like to feature flag.



 	
  * LaunchDarkly supports both boolean and multivariate feature flags. Boolean flags return true and false, but multivariate flags can return strings, number, JSON objects/arrays. You should hold a brainstorming session where everyone can identify the existing components they would like to flag.




#### 6. Setting up your feature flags


If you have existing flags, you can use LaunchDarkly’s [REST API](http://apidocs.launchdarkly.com/) to import your existing flags.



 	
  * You can also use the API to bulk create new flags or simply use the LaunchDarkly UI.


To organize and document your feature flags, LaunchDarkly lets you add a name, description, and tags to each feature flag.

 	
  * You can also name and provide descriptions for variations

 	
  * Your team should decide the best ways to standardize naming conventions




#### 7. Invite your team and start releasing faster with less risk


The coordinator should onboard team members, help set up projects and environments, and ensure that permissions are properly calibrated.



 	
  * Develop guidelines for what new features need to flagged and how you will use LaunchDarkly to practice feature flag-driven development




#### We’re here to help!


We want to make the transition fast, easy, and productive for you and your entire team. Contact us at [support@launchdarkly.com](mailto:support@launchdarkly.com) and we will answer all of your questions, provide guidance, and help you get started.
