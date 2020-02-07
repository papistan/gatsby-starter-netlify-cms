---
author: zuhaibs
comments: false
date: 2019-12-20 20:22:55+00:00
layout: post
link: https://launchdarkly.com/blog/launchdarkly-bolsters-its-global-infrastructure-with-new-data-centers/
slug: launchdarkly-bolsters-its-global-infrastructure-with-new-data-centers
title: LaunchDarkly Bolsters Its Global Infrastructure with New Data Centers
wordpress_id: 194736
categories:
- Product Updates
tags:
- infrastructure
- performance
- streaming architecture
---

## Initial connection times vastly improve for customers in Asia-Pacific and Europe


Today, we are excited to announce that LaunchDarkly has added two data centers to our client streaming infrastructure in Asia-Pacific and Europe. The addition enables faster connections for LaunchDarkly customers who use our client SDKs to manage features and rollouts for users all over the world. Traffic is routed to the fastest data center based on an end user's location, resulting in faster delivery times and improved application performance.

The results have been significant. We’ve seen a nearly 50% decrease in client SDK initialization times in Europe and a whopping 90% in Asia-Pacific.

[caption id="attachment_194738" align="aligncenter" width="1469"][![APAC load times](https://blog.launchdarkly.com/wp-content/uploads/2019/12/APAC.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/12/APAC.png) Asia-Pacific initialization time[/caption]

[caption id="attachment_194739" align="aligncenter" width="1469"][![Europe initialization time](https://blog.launchdarkly.com/wp-content/uploads/2019/12/EU.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/12/EU.png) Europe initialization time[/caption]


### Performance as a priority


At LaunchDarkly, performance and reliability are extremely important to us. Our customers depend on us to deliver their features correctly at the right times, and we continuously seek ways to enhance our [enterprise-grade architecture](https://launchdarkly.com/features/enterprise-grade-architecture/). As an example, last year, we implemented synthetic testing in various global data centers to see how LaunchDarkly was performing in the wild for our global customers.

Based on test results and customer feedback, we saw that customers with large user bases in Asia-Pacific and Europe experienced slow load times when initially connecting to [LaunchDarkly’s feature management platform](https://launchdarkly.com/product/). Of course, once the initial connection is made, all flag evaluations are local and lightning-fast—we stream flag updates to every client in under 200ms, enabling you to make changes to your feature flags in critical moments.

Prior to these additions, the primary LaunchDarkly data center was located in Northern Virginia (AWS us-east-1), meaning users, regardless of where they were in the world, had to pay the cost for networking delays to connect to Virginia when initializing. So, we set out to reduce latency times for those users by adding client stream endpoints in those regions.


### How we reduced latency times


There are physical limitations to how quickly a network can pass information. If you are sending data halfway across the world, even the fastest networks cannot make that happen instantly. And each moment a customer waits is a moment a customer may abandon their task (or product!).

To reduce the time for delivery, one solution is to reduce the physical distance between data and customer. So, we placed new points of presence closer to our end users in Asia-Pacific and Europe to shorten the time for clients to fetch the initial payload, resulting in a ~50% decrease in client SDK initialization times in Europe and ~90% in Asia-Pacific.

Why didn’t we just use a CDN? Our SDKs rely on our powerful streaming architecture that allows them to maintain connections to LaunchDarkly and instantly respond to the updates you make. These new points of presence allow our clients to initialize and hold those connections in their local region, something an off-the-shelf content delivery network won’t do. First, we invested in creating our streaming architecture to allow us to rapidly deliver flag updates and ensure that all parts of your system stay coherent and that all customers receive a consistent experience. Now, we’re improving that experience by bringing the streamers closer to more customers.


### How global streaming impacts LaunchDarkly


With a globally distributed client streaming infrastructure, we are able to provide our customers with faster connection times and increased resilience. And this is only the beginning of a larger initiative. In 2020, we plan to add more endpoints around the world and in the United States to further improve performance for customers in all locations.


### How can I start using this today?


If you use one of our [client-side SDKs](https://docs.launchdarkly.com/docs/client-side-and-server-side) today, you are already benefiting from the speed increase! We’d love to hear from you if you’re seeing benefits for your team.

As always, feel free to email our Product Team at [feedback@launchdarkly.com](mailto:feedback@launchdarkly.com) with your comments and suggestions.
