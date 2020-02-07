---
author: johnkodumal
comments: false
date: 2017-10-20 16:35:39+00:00
layout: post
link: https://launchdarkly.com/blog/keeping-client-side-feature-flags-secure/
slug: keeping-client-side-feature-flags-secure
title: Keeping Client-Side Feature Flags Secure
wordpress_id: 2072
categories:
- Feature Management
tags:
- feature flags
- javascript
- SDK
- security
---

LaunchDarkly's JavaScript SDK allows you to access feature flags in your client-side JavaScript. If you're familiar with our server-side SDKs, setup for our JS SDK looks superficially similar—you can install the SDK via npm, yarn, or via CDN and be up and running with a few lines of code. However, if you dig a bit deeper into the[ source code](https://github.com/launchdarkly/js-client) and do an apples-to-apples comparison with our[ node SDK](https://github.com/launchdarkly/node-client), you'll see that our client-side SDK works completely differently under the hood.

There's one simple reason for this difference—security. Because browsers are an untrusted environment, our client-side SDK uses a completely different approach that allows us to serve feature flags to your users securely. While we've made our approach as secure as possible out of the box, there are three best practices that we recommend all companies follow to maximize security when using client-side feature flags.


### **1. Choose Appropriate Use Cases**


First, in a browser environment your entire JavaScript source code is fully exposed to the public. It may be minified and obfuscated, but obfuscation is not security. This means that if you're using client-side feature flags, you must be aware that anyone can modify your source code directly and bypass your feature flags. For example, if you have a code snippet like this:

    
    if (ldclient.variation('brand.new.feature', false)) {
    
      // show a brand new feature
    
    } else {
    
     // don't show the feature
    
    }


You can expect that any of your end users could inline edit the above code snippet in their browser window to show the brand new feature, bypassing the feature flag and its rollout rules entirely. This is a fact about how client-side feature flags work—not a limitation in the LaunchDarkly platform.

This doesn't mean that client-side feature flags are always a security vulnerability—it just means that there are some use cases where a client-side feature flag alone isn't appropriate. For example:



 	
  * **Launching a feature that is press-, publicity-, or competitor- sensitive.** In this situation, having a user enable the feature early could derail a launch, or tip your company's hand. Even the feature flag key itself (e.g. brand.new.feature) could be sensitive. In this scenario, you can't even afford to push the new front-end code to production prior to launch, even if it's kept dark.

 	
  * **Entitlements.** A client-side feature flag alone is not a sufficient control for locking users out of functionality that they shouldn't be able to access. In this case, a client-side feature flag is fine **assuming** it's coupled to a backend feature flag. For example, you can use the same feature flag (with the same rollout rules) on both the front-end (to disable a UI element) and the back-end (to control access to a REST endpoint triggered by that same UI element).


Using client-side feature flags securely starts with choosing appropriate use cases. Ultimately, the choice depends on whether or not you can expose your new feature’s code to users that may not have the feature enabled.


### **2. Enable Secure Mode to Protect Customer Data**


There's a corollary to the observation that all JS code is fully exposed to the public—**there is no way to securely pass authentication credentials to a 3rd party API from the front-end alone. **Because anyone can view source, any API key or token that you pass to a 3rd party API via client-side JS is immediately exposed to users. 

One solution to this problem is to sign requests—use a shared secret on the server-side to sign the data being passed to the 3rd party API to ensure that the data hasn't been tampered with, or the request hasn't been forged. Tools like Intercom[ take this approach](https://docs.intercom.com/configure-intercom-for-your-product-or-site/staying-secure/enable-identity-verification-on-your-web-product). In Intercom's case, request signing guarantees that a user can't fetch chat conversations for a different user.

LaunchDarkly follows this approach as well. We call this[ Secure Mode](https://docs.launchdarkly.com/v2.0/docs/js-sdk-reference#section-secure-mode), and when enabled, it guarantees that a user can't impersonate another user and fetch their feature flag settings. Our server-side SDKs work in tandem with our client-side JavaScript SDK to make Secure Mode easy to implement. We recommend that all customers enable Secure Mode in their production environments.


### **3. Use a Package Manager to Bundle the SDK**


There's another aspect of security that comes with using any 3rd party service in your JavaScript—protecting yourself in case that service is attacked. Our recommended best practice is to embed our SDK in your code using a package manager, rather than injecting the SDK via script tag. We offer easy installation with popular package managers like npm, yarn, and bower. This does put the onus on you to upgrade when we release new versions of our SDK, but at the same time it can reduce latency to fetch the SDK _and_ give you control in accepting updates.


### **Conclusion**


We go to great lengths to ensure the security of our customers and their end users. We follow industry best practices in the operation of our service (we recently completed our[ SOC2 certification](https://blog.launchdarkly.com/launched-launchdarkly-soc-2-certification/)) in addition to providing advanced security controls in our product such as[ multi-factor authentication](https://docs.launchdarkly.com/docs/multi-factor-authentication),[ scoped API access tokens](https://docs.launchdarkly.com/docs/api-access-tokens), and[ role-based access controls](https://docs.launchdarkly.com/docs/custom-roles). This approach to security extends to our client-side JavaScript SDK. By following the practices outlined here, you can ensure that your use of client-side feature flags keeps your data and your customers’ data safe.
