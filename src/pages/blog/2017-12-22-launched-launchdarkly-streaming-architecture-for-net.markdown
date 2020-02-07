---
author: arnold
comments: false
date: 2017-12-22 18:32:38+00:00
layout: post
link: https://launchdarkly.com/blog/launched-launchdarkly-streaming-architecture-for-net/
slug: launched-launchdarkly-streaming-architecture-for-net
title: 'Launched: LaunchDarkly Streaming Architecture for .NET'
wordpress_id: 2140
categories:
- Product Updates
tags:
- .NET SDK
---

### **What is it?**


Earlier this month we released the latest update to the .NET SDK. This update included a number of enhancements, regarding the SDKs ability to propagate feature flag updates quickly and efficiently. We added support for streaming flag updates via [Server-Sent Events](http://html5doctor.com/server-sent-events/) as an alternative to polling. [HTTP-based streaming](https://launchdarkly.com/how-it-works/?utm_source=launchdarkly_blog&utm_medium=organic) is favored over polling to reduce network traffic and propagate feature flag updates faster. This also enables users to harness the power of our [relay proxy](https://github.com/launchdarkly/ld-relay) with the .NET SDK.


### **Why did we do this? **


This update significantly improves the performance of flag updates for .NET applications and enables teams to take advantage of the latest platform features. This release may also be used in conjunction with the LaunchDarkly Relay Proxy. 


### **What does it mean for LaunchDarkly users like me?**


Upgrading will not require any code changes, and the streaming strategy will be used by default. Once your code is up and running with the latest version of the .NET SDK, you’ll immediately receive the benefits, including faster feature flag updates, and less outbound network traffic. Documentation for advanced configuration options can be found [here](https://docs.launchdarkly.com/v2.0/docs/dotnet-sdk-reference#section-streaming).


### **But I have a lot going on—what does this really mean for an enterprise customer like me?**


If you’re a heavy LaunchDarkly user, with hundreds, or even thousands of SDK instances out in the wild, the changes made in the newest update will be even more beneficial. Streaming architecture unlocks [relay proxy](https://github.com/launchdarkly/ld-relay) support for .NET users. With the .NET SDK set up in proxy mode, your servers can connect directly to hosts within your own datacenter instead of retrieving flag updates from LaunchDarkly’s API individually.


### **What should I be doing to prepare for this change? (Best practices on making the update.)**


Upgrading to the most recent version is as simple as changing the dependency version of “LaunchDarkly.Client” to the most recent version in your project files and package configurations. If you’re using Visual Studio, this can be done through the NuGet package manager UI. Otherwise, the NuGet command-line interface may be used. See [Microsoft's docs](https://docs.microsoft.com/en-us/nuget/consume-packages/reinstalling-and-updating-packages) for complete instructions.

As of 12/21/17, the most recent version is 3.4.0. 


### **Is there anything else I should know?**


Yes! We have more in store for our .NET SDK, including:



 	
  * Improved performance and memory usage when storing feature flags

 	
  * Improved logging

 	
  * Lighter use of dependencies

 	
  * [Support](https://support.launchdarkly.com/hc/en-us/articles/115002374068-Do-you-support-Redis-caching-) for caching flag configurations via redis




### **What if I have questions, who can I talk to?**


Reach out to the LaunchDarkly support team directly by submitting a request [here](https://support.launchdarkly.com/hc/en-us/requests/new).
