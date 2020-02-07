---
author: tracil
comments: false
date: 2018-10-11 18:00:10+00:00
layout: post
link: https://launchdarkly.com/blog/launched-clone-flags/
slug: launched-clone-flags
title: 'Launched: Clone Flags'
wordpress_id: 193433
categories:
- Product Updates
tags:
- clone flag
- copy flag
- feature flag
---

For large projects, you'll often want to create many similar feature flags for different features or parts of the application. Today, we're making it even easier to create multiple flags related to a single project with our Clone Flag functionality. When you clone a flag, LaunchDarkly will copy the full targeting configuration for all environments (including on/off state) from the original flag to the new flag.

With Clone Flags you can create one flag, and then quickly create many more flags based on that first flag. This new Clone Flag functionality is a way to create flag templates for operational use cases, create flags around a single project, or to help new team members correctly make new flags.

Clone Flags show up as a separate audit log entry than a creating a new flag from scratch, making it easier to differentiate what's happening when members of your team are making new flags. You can also clone a flag programmatically through the API using the existing Create Feature Flag route, and adding the `clone` query parameter. For example, [https://app.launchdarkly.com/api/v2/flags/:projKey?clone=:clonedFlagKey](https://app.launchdarkly.com/api/v2/flags/:projKey?clone=clonedFlagKey) (replacing `:clonedFlagKey` with the appropriate key for your source flag).

Clone Flag is available on all LaunchDarkly flags under the Settings tab. For more information on the new clone query in our Flag API, go to [https://apidocs.launchdarkly.com/docs/create-feature-flag](https://apidocs.launchdarkly.com/docs/create-feature-flag).
