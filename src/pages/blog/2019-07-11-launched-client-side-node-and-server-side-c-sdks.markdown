---
author: bwoskow
comments: false
date: 2019-07-11 16:38:30+00:00
layout: post
link: https://launchdarkly.com/blog/launched-client-side-node-and-server-side-c-sdks/
slug: launched-client-side-node-and-server-side-c-sdks
title: 'Launched: Client-Side Node.js and Server-Side C SDKs'
wordpress_id: 194098
categories:
- Product Updates
tags:
- c server-side
- C++
- Node.js
- node.js client-side
- SDKs
---

We're excited to announce two new LaunchDarkly SDKs: the **client-side SDK for Node.js** and **server-side SDK for C**! With this announcement, the two SDKs have been promoted to general availability (GA).

Although these SDKs are new to LaunchDarkly, the underlying technologies – Node.js and C – were already supported by our _server-side_ Node.js SDK and _client-side_ C SDK. With this in mind, you might be wondering about the difference between client-side and server-side SDKs.

In a nutshell:



 	
  * LaunchDarkly's client-side SDKs are designed for single-user contexts typically distributed as desktop, mobile, and embedded applications.

 	
  * LaunchDarkly's server-side SDKs are designed for multi-user systems such as web application servers.


[![](https://blog.launchdarkly.com/wp-content/uploads/2019/07/node-c-2-1024x341.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/07/node-c-2.png)

Take a look at [our documentation](https://docs.launchdarkly.com/docs/client-side-and-server-side) to learn more about the implications of using our client-side and server-side SDKs.

With this understanding in mind, we see that both of the SDKs expand support for using LaunchDarkly to new sets of software. The client-side SDK for Node.js expands our support for Node.js to client-side applications such as desktop applications or apps running on Node.js-enabled devices. The server-side SDK for C expands our support for C and C++ to server-side applications built in C or C++ which handle many concurrent users.

Check out the [client-side Node.js](https://docs.launchdarkly.com/docs/node-client-sdk-reference) and [server-side C](https://docs.launchdarkly.com/docs/c-server-sdk-reference) SDK reference guides for information on how to get started. If you have questions, please reach out to our support team at [support@launchdarkly.com](mailto:support@launchdarkly.com).
