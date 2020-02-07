---
author: rgulati
comments: false
date: 2018-08-16 12:30:11+00:00
layout: post
link: https://launchdarkly.com/blog/metrics-and-traces-for-launchdarkly-relay-proxy/
slug: metrics-and-traces-for-launchdarkly-relay-proxy
title: 'Launched: Metrics and Traces for LaunchDarkly Relay Proxy'
wordpress_id: 193274
categories:
- Product Updates
tags:
- datadog
- launchdarkly relay proxy
- ld-relay
- metrics
- prometheus
- stackdriver
- usage metrics
---

For many of our customers, managing the lifecycles of feature flags is important. Our platform has an audit log that provides real-time visibility into every feature flag change made in their systems. Some customers, however, want to simplify connectivity rules—for resources behind a firewall or secured network, to have an added layer of caching, or because they want to filter or sample events. No matter the reason, they accomplish this by leveraging the LaunchDarkly Relay Proxy (LD-relay).

As more customers have adopted the LD-relay, we’ve heard requests for help getting better visibility into those service metrics. So, we have added support for metrics and traces that customers can forward to standard monitoring tools—specifically those that are exported to DataDog, StackDriver, and Prometheus.


## Creating Configuration Files


To get started, you must have [the LD-relay proxy up and running](https://github.com/launchdarkly/ld-relay#quick-setup). Then, create a configuration file for one of the supported monitoring applications. For example, if you are using LD-relay to export metrics to DataDog your configuration file should look like this:


[datadog]
enabled = true
statsAddr = <URI>
traceAddr = <URI>
tag = <TAG_NAME>
prefix = <PREFIX_NAME>








You also want to make sure that your settings in DataDog are ready to begin consuming data:




api_key: YOUR_API_KEY
use_datadogstatsd: yes
dogstatsd_port : PORT
bind_host: localhost






## Types of Metrics


After you have completed these steps, you should see your ld-relay metrics (in this case, DataDog). For all three monitoring applications, we provide metrics such as the number of requests received, the number of open streaming connections, and route traces. With this information, you will have insight into how the relay proxy is performing.

To get started, check out the LD relay [github](https://github.com/launchdarkly/ld-relay). If you have any further questions about LD-relay or LaunchDarkly please contact us at [support@launchdarkly.com](mailto:support@launchdarkly.com).
