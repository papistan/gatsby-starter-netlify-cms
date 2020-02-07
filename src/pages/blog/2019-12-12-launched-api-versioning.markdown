---
author: kirani
comments: false
date: 2019-12-12 16:00:42+00:00
layout: post
link: https://launchdarkly.com/blog/launched-api-versioning/
slug: launched-api-versioning
title: 'Launched: API Versioning'
wordpress_id: 194586
categories:
- Product Updates
tags:
- APIs
---

At LaunchDarkly, we strive to keep our REST API backward compatible, but we occasionally have to make changes in the process of shipping new features that could break that backward compatibility. These breaking changes may cause unexpected behavior if you’re not set up to handle them accordingly.

Updates to newer versions of LaunchDarkly’s REST API include support for the latest features and critical improvements. However, we understand that updating your LaunchDarkly API version may not always make it to the top of your task list, which is why **we now provide simultaneous support for multiple API versions.** This allows you to migrate from your current API version to a new version when you’re ready, without forcing you to do so by fear of breaking something.

_See new API versions in the [Changelog](https://apidocs.launchdarkly.com/reference-link/changelog)._


### How to use API versions


You can set the API version on a specific request by sending an LD-API-Version header, as shown in the example below:

[![Launch-Darkly-API-version-screenshot](https://blog.launchdarkly.com/wp-content/uploads/2019/12/Screen-Shot-2019-12-13-at-11.20.51-AM-300x121.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/12/Screen-Shot-2019-12-13-at-11.20.51-AM.png)

When creating an [access token](https://docs.launchdarkly.com/docs/api-access-tokens), you must specify a version of the API to use. This version corresponds with a number that represents the date of the API version release. This ensures that integrations using this token honor the chosen API version, and cannot be broken by changes in new version releases.

Previously-created tokens have their version set to 20160426 by default, so that they continue working the same way they did before the option for versioning was introduced. If you would like to upgrade your integration to use a new API version, you can explicitly set the header described in the example above.


### Bonus


**Best practice:** We recommend that you set the API version header explicitly in any client or integration you build and only rely on the access token API version during manual testing.


### Get started


As users of LaunchDarkly ourselves, we always strive to provide the best developer experience while enabling continuous delivery. To learn more about API Versioning and get started, check out our [documentation](https://apidocs.launchdarkly.com/reference?showHidden=7f3f4#versioning). If you have feedback, contact [feedback@launchdarkly.com](mailto:feedback@launchdarkly.com) or contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com) to start a free trial today!
