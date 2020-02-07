---
author: kirani
comments: false
date: 2019-10-10 22:48:18+00:00
layout: post
link: https://launchdarkly.com/blog/launched-datadog-integration/
slug: launched-datadog-integration
title: 'Launched: Datadog Integration'
wordpress_id: 194369
categories:
- Product Updates
tags:
- datadog
- infrastructure
- monitoring
- monitoring infrastructure
---

LaunchDarkly makes it easier for teams to deploy features more confidently by doing so with flags, thus reducing the associated risks in production. Teams that use Datadog to monitor the performance of their systems can now use LaunchDarkly's Datadog integration to visually correlate and understand how feature deployments impact their application and infrastructure metrics.

This integration pushes events from LaunchDarkly and overlays them in the Datadog Events dashboard to improve visibility and context of changes across all systems. This makes it easier to detect and resolve harmful changes to system performance as a result of feature flags that are turned on or off.

For example, if a flag is enabled that causes a service to significantly slow down, the DevOps team will now have the LaunchDarkly context inside their Datadog dashboards – enabling them to understand what triggered the issue.

![](https://blog.launchdarkly.com/wp-content/uploads/2019/10/ld-datadog-hover.gif)

**Guillame Clochard, an engineer from iAdvize**, recently enabled the integration for his team. Here's what he had to say:


<blockquote>"The LaunchDarkly Datadog integration helped us monitor precisely how our flags change and, by creating alerts in Datadog, we are able to notify the corresponding team if a critical operational flag is modified."</blockquote>


We are confident the Datadog integration improves the ability for teams to monitor and control the health of their production systems while enabling continuous delivery. To learn more about this integration and get started, [check out our documentation](https://docs.launchdarkly.com/docs/datadog). If you have questions about LaunchDarkly, contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com) or start a free trial today!
