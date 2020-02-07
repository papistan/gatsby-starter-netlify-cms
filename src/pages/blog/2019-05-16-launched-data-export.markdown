---
author: sagarwal
comments: false
date: 2019-05-16 17:22:39+00:00
layout: post
link: https://launchdarkly.com/blog/launched-data-export/
slug: launched-data-export
title: 'Launched: Data Export'
wordpress_id: 193889
categories:
- Product Updates
tags:
- analytics
- data export
- experimentation
---

Many LaunchDarkly customers use hundreds of feature flags to safely deploy new code to production, test and evaluate new features, and provision customized experiences for their users and customers. As teams grow their use of LaunchDarkly, we've come to understand that data teams at our customers want more robust information about how their users are interacting with LaunchDarkly feature flags.

With our enhanced Data Export product, LaunchDarkly customers can receive a real-time feed of all full-fidelity feature flag evaluations via Amazon Kinesis and Google PubSub, with Segment coming soon.

LaunchDarkly's Data Export allows customers to conduct sophisticated analysis for experimentation or A/B testing purposes, to easily troubleshoot and debug the most obscure of bugs, and to enrich their customer profiles with feature flag evaluations.

Data Export provides customers with the means to quickly connect their live streams of LaunchDarkly evaluations to Amazon Redshift, Google BigQuery, Snowflake, or other data warehouse options. Using these robust and well understood message queue services allow data engineers to quickly consume LaunchDarkly feature flag evaluations and run sophisticated analyses on the information received. And with LaunchDarkly's [evaluation reasons](https://docs.launchdarkly.com/docs/evaluation-reasons), teams can quickly understand not just what variations users received, but why those users received those variations.

With LaunchDarkly's Data Export, large enterprises will be able to run sophisticated personalization to deliver customized experiences for their users and customers. Data Export is only available to LaunchDarkly customers on Enterprise plans. You can get more information about [LaunchDarkly's Data Export here](https://docs.launchdarkly.com/docs/data-export); to get started with Data Export, please contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com) or reach out to your Account Executive.
