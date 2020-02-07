---
author: arun
comments: false
date: 2018-07-12 20:12:28+00:00
layout: post
link: https://launchdarkly.com/blog/launched-public-ip-list-endpoint/
slug: launched-public-ip-list-endpoint
title: 'Launched: Public IP List Endpoint'
wordpress_id: 193186
categories:
- Product Updates
tags:
- feature management
- IP endpoint
- public IP address
- security
---

At LaunchDarkly we know our customers value continuous improvement, but we're also aware that our feature management platform is a trusted part of our customers' infrastructure. Because security and service availability are just as important as new features, we strive to balance these concerns as we maintain and update our service.

Starting on **July 16**, we are making infrastructure changes to improve the scalability and resilience of our public-facing edge infrastructure. As a result, our service's public IP addresses will begin to change.

Most customers will not need to make any updates, but we know that some customers maintain firewalls or external proxies restricting outbound network traffic to specific trusted services. While domain-based whitelisting provides a good balance of security and flexibility, some customers require securing traffic by IP addresses. Previously, customers would have to ask us for LaunchDarkly's public IP addresses. As part of this infrastructure migration project, we've built a new endpoint that reports all of the [public IP address ranges](https://app.launchdarkly.com/api/v2/public-ip-list) for LaunchDarkly services. With this endpoint, you can automatically update IP-based whitelists as we roll out changes to our infrastructure. We have also [documented this new endpoint](https://apidocs.launchdarkly.com/docs/public-ip-list) in the LaunchDarkly API reference guide. We will post informational updates to our [status page](https://status.launchdarkly.com/) as we add new IP address ranges to this list.

If you have any questions, feel free to reach out to us at [support@launchdarkly.com](mailto:support@launchdarkly.com).
