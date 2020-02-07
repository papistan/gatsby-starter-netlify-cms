---
author: jbeasley
comments: false
date: 2018-10-03 16:25:23+00:00
layout: post
link: https://launchdarkly.com/blog/multivariate-feature-flags-in-practice/
slug: multivariate-feature-flags-in-practice
title: Multivariate Feature Flags in Practice
wordpress_id: 193418
categories:
- DevOps
- Feature Management
tags:
- configuration flags
- feature flags
- feature management
- front end monitoring
- JSON
- JSON flags
- multivariate feature flags
- numeric flags
---

Most discussion of feature flagging focuses on binary, on-off flags and how they can reduce friction in shipping software. These simple binary switches can do a lot! When used with targeting rules that specify exactly where and when that flag is on or off, binary switches enable transformative workflows for software development like continuous delivery, progressive delivery and testing in production.


However, binary flags are not the only type of feature flag. Controlling more complex scenarios than just toggling a small feature on or off requires more than a simple on-off switch. This is why LaunchDarkly supports multivariate flags—also known as flags of types other than bool. In this post, I will walk through a few interesting use cases of such flags to show when and why we reach for these more expressive flags at LaunchDarkly.


### Numeric Flags


The clear next step up in complexity from boolean flags is numeric flags. If a flag can be a zero or one, then why not any number? Numeric flags open up many more possibilities, but there are two different possible use cases I'd like highlight here: true multi variate flagging and flags as configuration values.


### Multivariate Numeric Flags


If we think of multivariate flags as "mode" switches for a feature that has more than two clear states, then the numbers served by the flag can map to each of those distinct states. A common example of these "multivariate" flags is testing several different designs for a feature to determine which works best for users. Think testing and comparing three different designs for a search box and determining which enables users to find what they are looking for the fastest. More discussion of these kinds of flags can be found in our [blog post introducing them](https://launchdarkly.com/blog/the-future-of-feature-flags-managing-dynamic-applications/).

While design variations are the most common example, multivariate flags are also incredibly useful for backend development. Take, for example, a service that validates JSON. The performance of this service would naturally be a factor of the implementation of JSON deserialization used in the service. If this service is written in Go, there are [many](https://golang.org/pkg/encoding/json/) [options](https://github.com/buger/jsonparser) [for](https://github.com/pquerna/ffjson) [JSON](https://github.com/antonholmquist/jason) [deserialization](https://github.com/bitly/go-simplejson) that all perform differently depending on the specific workload of the JSON service in question. Typically, comparing these implementations would require creating a benchmark with a realistic workload. Instead, you can use a multivariate flag to ship a version of the service that contains the different implementations to production, so that you can use that flag to try the variations and observe which works the best for the actual workload the service runs on. If one or more prove to be problematic, then the flag makes it easy to switch back to the implementation that performs better.


### Numeric Configuration Values


Numeric flags are also useful for setting an important "magic number", as numeric flags allow that magic number to change as the requirements for that feature change. For this case, flags can be used where one might put an integer constant at the top of a file when the value might not be set in stone.

At LaunchDarkly, we use these kinds of flags in a feature that creates warnings and limits for the number of specific user targets that can be applied to a segment or flag. Targeting many individual users [negatively affects performance](https://support.launchdarkly.com/hc/en-us/articles/360002401874-Why-should-I-avoid-individually-targeting-too-many-users-). We wanted to surface this fact directly on the flag and segment targeting pages, and recommend customers use LaunchDarkly’s custom attribute feature to target large numbers of users. In our implementation, we show a warning when more than 10,000 individual users are targeted with a link to a support document, and enforce a hard cap at 50,000 users. There is no particular technical reason for why we chose a limit of 50,000 users rather than 40,000 or 60,000—it was a threshold that we picked after analyzing the real-world use of individual targets throughout our customer base. Large user lists make environment sizes bigger, which makes SDK initialization slower and SDK memory use higher. But there is no clear limit where a customer’s performance degrades unacceptably due to their use of large number of individually named targets.

For our implementation, we created two flags—one for the warning and one for the limit, rather than declaring constants in code. These flags let us separate the process of determining the right limits to set, from the process of getting the code into production. It bought us the flexibility to change these values as our infrastructure evolves without any additional code changes. Furthermore, if we need to special case a specific customer for whom standard 10K and 50K limits might be unnecessary, we can change our targeting rules on the flags to give them a special limit instantly, without a code deploy. If this feature had broader implications and impact, we could have A/B tested our limits to try to determine which limits and warnings have the desired effect of reducing the size of large environments to improve performance.


### JSON Flags


Sometimes a numeric flags are not expressive enough to specify the behavior that should be controlled in flag, rather than in code. In these cases, serving JSON variations offers a powerful mechanism for decoupling some of the decisions about the precise behavior of a feature from the development and deployment of the code behind it. To illustrate this process, I will discuss two cases where we use JSON flags at LaunchDarkly.


### Frontend Monitoring


At LaunchDarkly, we monitor page loads on [app.launchdarkly.com](https://app.launchdarkly.com) through a bare-bones agent that forwards performance metrics exposed by the browser to an internal API endpoint after the page load event. This setup is inspired by one Honeycomb described in a [blog post](https://www.honeycomb.io/blog/2017/11/instrumenting-browser-page-loads-at-honeycomb/) detailing their browser monitoring setup, with a few tweaks to leverage feature flags to decouple determining what to collect from how we collect it. The goal with our agent is give anyone at LaunchDarkly the ability to start collecting a specific metric from browsers simply by changing a flag value.

Below is the agent code we use to collect metrics from our WebApp:

    
    <code class="" data-language="javascript">import { Record, Map, Set, fromJS } from "immutable";
    
    function collectWindowMetrics(trackedWindowMetrics) {
      // Build a map by iterating over the flag value
      return trackedWindowMetrics.reduce((map, metric) => {
        // Repeatedly address into the window object to find value
        // A metric of 'navigator.userAgent' would add the value at window['navigator']['userAgent'] to the
        // result map
        // A metric of 'navigator.useragent' would reach the value at window['navigator']['useragent'], which
        // is undefined, and add nothing to the map
        // A metric of 'nvgtr.userAgent' would reach the value at window['nvgtr'], which is undefined, and
        // add nothing to the map
        const value = metric.split(".").reduce((val, key) => {
          if (typeof val !== "undefined") {
            return val[key];
          } else {
            return undefined;
          }
        }, window);
        if (typeof value !== "undefined") {
          return map.set(metric, value);
        } else {
          return map;
        }
      }, new Map());
    }
    
    function sendMetrics() {
      const user = {}; // Add useful user attributes
      var ldclient = LDClient.initialize("YOUR_CLIENT_SIDE_ID", user);
    
      // Wait for client to init
      ldclient.on("ready", () => {
        // Pull JSON config from LaunchDarkly and load into immutable
        const trackedWindowMetrics = Set(
          fromJS(ldclient.variation("METRICS_FEATURE_KEY", {}))
        );
    
        // trackedWindowMetrics will look something like this:
        // [
        //   "navigator.language",
        //   "innerHeight",
        //   "innerWidth",
        //   "screen.height",
        //   "screen.width",
        //   "navigator.connection.effectiveType",
        //   "navigator.connection.rtt",
        //   "navigator.connection.downlink"
        // ];
    
        // Collect metrics using the JSON config
        const metrics = collectWindowMetrics(trackedWindowMetrics);
        // Send metrics to a collector endpoint here
    
        // metrics.toJSON() will look something like:
        //{
        //  "innerHeight": 980,
        //  "innerWidth": 1720,
        //  "navigator.connection.downlink": 5.15,
        //  "navigator.connection.effectiveType": "4g",
        //  "navigator.connection.rtt": 100,
        //  "navigator.language": "en-US",
        //  "screen.height": 1440,
        //  "screen.width": 3440
        //}
      });
    }
    
    window.addEventListener(
      "load",
      () => {
        // Wait for load to complete
        setTimeout(() => sendMetrics(), 0);
      },
      false
    );</code>


With a minimal amount of code, we get a pretty flexible system for collecting metrics. If we forgot a metric, we simply add it to the JSON metrics list flag and data collection for that new metric begins almost instantly without the need to make a code change or deploy new code.

We round out our frontend monitoring with a similar flag-based system to collect performance timing data from the fantastic [performance timeline API](https://www.w3.org/TR/performance-timeline/), using older APIs to fill in when needed, and convert it into trace form to gain visibility into what might have made a long page load slow.


### Conclusion


Boolean feature flags are great for decoupling shipping code from releasing features. Numeric and JSON multivariate flags make feature flags more expressive and allow specific behavior of a new feature to be decoupled from shipping the code that backs that feature. These more expressive flags let developers ship code first and work out details later, with the benefit of real data and real customer feedback.
