---
author: mcho
comments: false
date: 2019-07-26 17:52:24+00:00
layout: post
link: https://launchdarkly.com/blog/launched-support-for-oauth-2-0/
slug: launched-support-for-oauth-2-0
title: 'Launched: Support for OAuth 2.0'
wordpress_id: 194156
categories:
- Product Updates
tags:
- OAuth
- REST API
---

We're getting ready for more integrations and wanted to make it easier for customers to build out their own applications on top of LaunchDarkly, so we've launched support for the OAuth 2.0 standard as a service provider.

If you want to use our REST APIs to build your own dashboards, reports or services, you can securely authorize to LaunchDarkly:



 	
  * Second-party built applications and services can authorize with us without having to expose user tokens or type passwords

 	
  * Your Identity Provider can authorize with us and enable SCIM support, including custom role data to align with your user groups

 	
  * Third party applications and integrations will be able to securely authorize using OAuth


OAuth apps will never have permission to do more than you can do in LaunchDarkly. [Read more](https://docs.launchdarkly.com/docs/authorizing-oauth-applications) in our docs, and contact us (support@launchdarkly.com) to obtain OAuth credentials for your applications.
