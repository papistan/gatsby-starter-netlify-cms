---
author: justinucd
comments: false
date: 2016-06-29 17:45:15+00:00
layout: post
link: https://launchdarkly.com/blog/launched-event-stream-api/
slug: launched-event-stream-api
title: 'Launched: Event Stream API'
wordpress_id: 943
categories:
- Product Updates
tags:
- analytics
- api
- event stream api
- LaunchDarkly
---

One of LaunchDarkly’s core strengths is that the entire product is driven by a [REST API](http://apidocs.launchdarkly.com/).  This means that everything in the app can be accessed programmatically-- including [modifying feature flags](https://docs.launchdarkly.com/v1.0/docs/environments), [goals](https://docs.launchdarkly.com/v1.0/docs/optimizely), [accessing A/B test results](https://docs.launchdarkly.com/v1.0/docs/running-an-ab-test), and more.

There was one notable exception to this— we did not provide a way for customers to access their raw analytics events. This can be a huge amount of data, so a normal queryable REST API is not the most reasonable solution.

**Real-Time Event Stream API**

To fill this gap, we have launched an event stream API that provides a real-time stream of raw analytics data.  These events include feature flag requests, analytics events, custom events, and more. 

[![LaunchDarkly Event Stream API A/B Testing Analytics and Data](https://blog.launchdarkly.com/wp-content/uploads/2016/06/eventstream_branding.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/06/eventstream_branding.jpg)

**Benefits**

Customers can harness the event stream API for their own internal analytics platforms or build custom integrations tailored to their specific needs.  You can then leverage user data to analyze metrics like conversions, revenue, and application performance.

**Connecting to the stream**

Accessing the API is simple. This is how to do it with curl:

    
    curl -H "Authorization: api_key YOUR_API_KEY" -H "Accept: text/event-stream" https://stream.launchdarkly.com/events


Check out the [documentation](https://docs.launchdarkly.com/v2.0/docs/analytics-data-stream-ads) for more information.
