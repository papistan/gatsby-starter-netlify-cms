---
author: bwoskow
comments: false
date: 2019-06-28 16:30:13+00:00
layout: post
link: https://launchdarkly.com/blog/launchdarkly-sdk-update-hard-things-in-computer-science/
slug: launchdarkly-sdk-update-hard-things-in-computer-science
title: 'LaunchDarkly SDK Update: Hard Things in Computer Science'
wordpress_id: 194008
categories:
- Product Updates
tags:
- . php
- .net
- android
- c client-side
- c server-side
- electron
- go
- iOS
- Java
- javascript
- Node.js
- Python
- React
- React Native
- ruby
- SDKs
- Xamarin
---

<blockquote>There are only two hard things in Computer Science: cache invalidation and naming things.

-- Phil Karlton</blockquote>


This is _not_ a blog post about cache invalidation. Apologies to all of the cache enthusiasts out there. Rather, this is a blog post about naming things!

When LaunchDarkly was founded in 2014, we envisioned that our customers would embed LaunchDarkly-provided libraries into their applications to easily manage all interactions with our feature flagging services. The first library we released was `java-client` with `go-client`, `php-client`, and `ruby-client` following shortly thereafter. The library names were given `-client` suffixes because of their role as client libraries to use LaunchDarkly.

As LaunchDarkly grew, so did the collection of client libraries. By 2015 there was a growing problem — some of the newer client libraries were intended for use on client-architected applications whereas the original libraries were intended for server-based architectures. This distinction fundamentally impacts how the LaunchDarkly client library operates; in server-architected applications the library concurrently handles many users and evaluates flags itself whereas in client-architected applications the library handles one user at a time and delegates to the LaunchDarkly service for flag evaluation. Herein starts our problem with naming things; how do you distinguish client-side libraries and server-side libraries when they are all referred to as _clients_? Consequently, the decision was made to refer to these libraries as SDKs. However, the libraries' artifacts and their corresponding GitHub repositories weren't updated to reflect this decision. They continued to have `-client` monikers.

Fast forward to the present and we're finally addressing our naming problems. Today, we're announcing that each of our libraries are consistently referred to as SDKs and with a clear distinction of whether they are intended for server-side and client-side purposes.

For our customers, this resolution impacts very little — existing SDK versions will continue working as before. However, you'll need to take minor actions when updating to the latest versions of our SDKs.

[WPSM_AC id=193917]


### But Wait, There's More!


LaunchDarkly open-sources its SDKs and welcomes contributions from the community. To improve the developer experience, all LaunchDarkly SDKs now possess a README adhering to a consistent template as well as contribution guidelines with instructions for building and testing the code.
