---
author: justinucd
comments: false
date: 2016-09-20 22:09:13+00:00
layout: post
link: https://launchdarkly.com/blog/launched-prerequisites-for-flag-dependencies/
slug: launched-prerequisites-for-flag-dependencies
title: 'Launched: Prerequisites for Flag Dependencies'
wordpress_id: 1097
categories:
- Product Updates
tags:
- experiments
- feature flags
- feature toggles
- flag dependencies
- prerequisites
---

To perform smarter, conditional feature releases, our customers have asked for the ability to control feature dependencies in LaunchDarkly. In other words, they wanted to evaluate Flag B only if Flag A was “on” for a particular user.

For example, let’s say we have a feature flag that controls the visibility of a checkout flow with multiple steps. Within that flow, we have additional feature flags that control smaller elements, like a button and a modal. We want to make sure that the checkout flow is actually “on” for a user before we evaluate the flags for buttons and modals.

To provide this functionality, we have launched [Prerequisites](http://docs.launchdarkly.com/docs/prerequisites) (beta), which lets you add a list of flags and their expected values as prerequisites to enable a feature.


### Prerequisite Example


Let's say we have two flags that control an API: api_reads and api_writes. In this case, it makes no sense to have write access to the API if you do not have read access. With prerequisites, you can make sure that api_reads is “on” with the user receiving `true` before api_writes is evaluated for that user.

You can manage your prerequisites in the feature flag's Targeting tab:

[![LaunchDarkly Feature Flag / Toggle Dependencies - Prerequisites](https://blog.launchdarkly.com/wp-content/uploads/2016/09/e410d36-doc_pre.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/e410d36-doc_pre.jpg)

You can add as many prerequisites as you want to a feature flag. We have checks built in to ensure that there are no circular dependencies and that deleted flags are automatically removed as dependencies.


### Example Use Case


**Mutually exclusive experiments**

Let’s say we want to test whether the size or color of a button affects user engagement, but we want to run these two experiments at the same time.  Prerequisites gives you the ability to compartmentalize experimentation , allowing you to run exclusive experiments without hardcoding the logic into your codebase.  In this case, we want to ensure that users who receive the button size experiment do not receive the color experiment.

First, we have a feature flag that shows a _**red**_ button to 50% of users:

[![LaunchDarkly Feature Flag Rollout](https://blog.launchdarkly.com/wp-content/uploads/2016/09/50rollout-1.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/50rollout-1.png)

Second, we have a feature flag that shows a _**big**_ button to all users who are receiving `false` for the 'Red Button' flag:

[![LaunchDarkly Feature Flag Rollout - Prerequisite flag dependency](https://blog.launchdarkly.com/wp-content/uploads/2016/09/big_button-1.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/big_button-1.png)

In other words, all users who receive `true` for the Red Button flag will receive `false` for the Big Button flag.   This means that no user will get _**Red**_ and _**Big**_ for their button style.

Here is some example code (Java):

    
    boolean showRedButton = client.boolVariation("red-button", user, false);
    boolean showBigButton = client.boolVariation("big-button", user, false);
    
    if (showRedButton) {
     	// Display the red button
    }
    
    if (showBigButton) {
    // display the big button
    }


However, what if you now want to test making the button both_ **Red**_ and _**Big **_?  You can do that with LaunchDarkly by simply changing the prerequisite value to `true`:

[![LaunchDarkly Feature Flag / Toggle Prerequisites - Inclusive Experiment](https://blog.launchdarkly.com/wp-content/uploads/2016/09/inclusiveexperiment-1.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/09/inclusiveexperiment-1.png)

No code changes are needed. The beauty of this example is that your experiments are completely decoupled from your codebase.

There are many exciting ways to use prerequisites, especially when you take full advantage of our [multivariate](https://blog.launchdarkly.com/launched-multivariate-feature-flags/) feature flags and [custom rules](https://blog.launchdarkly.com/launched-custom-targeting-rules/).  If you have any questions or feedback, please send them to [support@launchdarkly.com](mailto:support@launchdarkly.com) and we’ll be happy to help!
