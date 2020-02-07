---
author: justinucd
comments: false
date: 2016-12-06 18:01:18+00:00
layout: post
link: https://launchdarkly.com/blog/feature-flag-driven-products/
slug: feature-flag-driven-products
title: Feature Flag-Driven Products
wordpress_id: 1228
categories:
- Feature Management
tags:
- consistency
- feature flags
- feature toggles
- personalization
- plan management
---

### Using feature flags for plan management, personalization, and cross-platform consistency


When feature flags/toggles were first introduced, their primary purpose was to mitigate risk and manage software releases.  We would use these toggles to turn features “on” or “off”, and gradually roll out new features to customers.  If something went wrong or if customers didn’t like the new feature, we could kill it without redeploying.

What developers started realizing is that we could use feature flags to manage dynamic content and have long-term control over every application feature.  This means that toggles would not just be “on” or “off”, “true” or “false.”  Rather, they could serve strings, numbers, JSON objects, and JSON arrays -- allowing us to serve dynamic content and use feature flags to perform more interesting functions.




## Plan Management


Almost every product has a series of plans made of bundled features.  Plans typically have two parameters: a feature and a value.  A feature can be something like a VIP Area, enhanced support, or additional customizations.  Values are attributes of features, and can be something like “20” members, “5” teams, and “enhanced” speed.

Using feature flags, we can easily determine which features belong to which plans, and edit bundles as we add new features or change their values.

Here, we have two plans: Standard and Gold.  The Standard plan allows for 10 members, while the Gold plan allows for 50 team members and a VIP area.

[![LaunchDarkly Plan Management with Feature Flags and Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/12/plan_management.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/plan_management.png)

We constructed two flags: team_count and vip_area.   For team_count, we created a [multivariate](https://blog.launchdarkly.com/tag/multivariate-feature-flags/) feature flag that returns the numbers 50, 10, and 1.  We then have a rule that checks if the “plan” attribute matches “standard” or “gold” to determine which value to serve.  The “plan” attribute would belong to a user object, which could look something like this:

    
    {
      "key": "aa0ceb",
      "firstName": "Ernestina",
      "lastName": "Evans",
      "email": "ernestina@example.com",
      "custom": {
        "plan": ["Gold"]
      }
    };


Because Ernestina’s plan attribute has a value of “gold”, she would receive a 50 team member limit and have access to the VIP area.

Moreover, we could use multivariate flags to dynamically modify pricing.  For example, we could toggle prices on-load based on whether the the user is a “VIP” or “NEW”.

[![LaunchDarkly Pricing Management with Feature Flags / Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/12/pricing_management.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/pricing_management.png)

In this example, all “new” users receive a discounted price of $50 and “VIP” users see a discounted price of $20, while all other users receive the normal $75 price.

Other pricing use cases would be localization, seasonality, and discount codes.  We could manage these separate from our application logic, giving us more flexibility without having to redeploy.




## Personalization & Styling


We can also use feature flags to manage styling and personalized themes, essentially using these toggles as a quasi-content management system.

Here, we use a multivariate flag to serve color hex values, turning a feature orange, blue, or green:

[![LaunchDarkly Multivariate Feature Flags / Feature Toggles for dynamic application management](https://blog.launchdarkly.com/wp-content/uploads/2016/12/multivariateff.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/multivariateff.png)We could also serve pre-defined CSS class names to add or remove properties from elements.  This allows us to separate some of this logic from our primary codebase.  While this shouldn’t be used for primary layout and styling, it could be used to serve particular to styles or to customize themes based on user attributes.

For example, if I had a user with a ‘theme’ attribute that has a value of ‘blue’, then I could serve the blue CSS class, which my application logic would append to the relevant elements.




## Consistent Cross-Platform Experiences


Cross-platform feature flagging is an easy way to deliver personalized and consistent user experiences across different platforms.  If our product has features that are shared on a web and mobile platforms, we can use one flag to control the visibility of both those features.

Here, we have a user who is receiving the TRUE variation for the VIP feature flag.

[![LaunchDarkly Consistent Mobile and Web Experiences using Feature Flags / Toggles](https://blog.launchdarkly.com/wp-content/uploads/2016/12/syncff.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/syncff.png)

Even though the web and mobile platforms have different permutations of the feature, the same flag could synchronize the VIP experience between both platforms.

Some more benefits of cross-platform feature flagging include:



 	
  * The ability to decide whether to release a cross-platform feature simultaneously or separately, with full control over who gets to see that feature. For example, web users might get access to a new search bar before mobile users do.

 	
  * Real time personalization that allows users to opt-in to new features on one platform (like mobile) and have that personalization sync with another platform (like web)

 	
  * Percentage rollouts that allow us to gradually release a feature to targeted users on different platforms, allowing us to assess user and performance feedback for each platform

 	
  * A kill switch that lets us turn off poorly performing features for web and mobile, without having to redeploy





## Flag Management


The process of [feature flagging](https://blog.launchdarkly.com/feature-flag-driven-development/) is fairly straightforward: we wrap our features in conditionals that determine who can see the features and when. At an enterprise scale, organizations must confront the complexities of mitigating [technical debt](https://dzone.com/articles/feature-toggles-are-one-worst), managing developer workflows, compliance, and controlling the lifecycle of feature flags.

One of the biggest pain points around traditional feature toggles is that marketing or business teams would need to create engineering tickets to get their requests updated.  These toggles would be typically controlled within the codebase itself, like a config file or database.

By adding a user interface for flag management, we can empower non-technical teammates with the ability to target users, perform rollouts, or run beta tests.  This even makes it easy for engineers to coordinate flag creation, mitigate technical debt, and manage the lifecycle of their flags.

[![LaunchDarkly Feature Flag / Toggle Management Dashboard](https://blog.launchdarkly.com/wp-content/uploads/2016/12/ff_dashboard.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/12/ff_dashboard.png)

Some other benefits of UI flag management:



 	
  * Flag Implementation & Consistency – Feature flags need to be carefully crafted and consistently implemented within our application to prevent performance degradation and ensure that they function correctly. Often times, organizations will use conflicting methods like managing multiple config files or using in-line toggling.

 	
  * Flag Scalability – Adding more feature flags makes testing and management exponentially more difficult over time. It becomes very hard to tell which flags are necessary or obsolete.

 	
  * Flag Management – Maintaining feature flags across multiple development environments (local, QA, staging, production) becomes arduous and time-consuming. It becomes increasingly difficult to track who created the flag, the flag’s intended use, and changes made to the flag’s rollout.


