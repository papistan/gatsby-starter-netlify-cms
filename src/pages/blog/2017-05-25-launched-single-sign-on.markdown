---
author: arun
comments: false
date: 2017-05-25 17:28:55+00:00
layout: post
link: https://launchdarkly.com/blog/launched-single-sign-on/
slug: launched-single-sign-on
title: 'Launched: Single sign-on'
wordpress_id: 1627
categories:
- Product Updates
tags:
- Enterprise
- LaunchDarkly
- security
- single sign-on
---

Spend some time at a software shop, and you'll inevitably collect a pile of accounts for services, internal and external. Since you value security, each of your passwords are long and unique and safeguarded in a password manager. You imagine a world where you don't need to manage passwords for each and every service you use.

That's why we are excited to announce support for [single sign-on](http://docs.launchdarkly.com/docs/single-sign-on) via the industry-standard Security Assertion Markup Language 2.0 (SAML 2.0). Knowing that SAML integrations can be cumbersome and complicated, we refined the administrator experience to be simple and clear. We built a test-drive mode so administrators can verify their SAML configuration end-to-end before enabling single sign-on in LaunchDarkly for the entire team.

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/05/sso.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/05/sso.png)

Our single sign-on implementation is accompanied by a couple other benefits. With LaunchDarkly's just-in-time user provisioning, administrators can onboard new employees from their identity provider without having to also create accounts for them in LaunchDarkly. Simply grant the new employee access to LaunchDarkly via your identity provider. Then LaunchDarkly will automatically create a new account when the member visits LaunchDarkly for the first time. Additionally, any changes to the member's profile or assigned [roles](http://docs.launchdarkly.com/docs/teams) will be propagated from your identity provider as soon as the member signs into LaunchDarkly.

We currently support [Okta](https://www.okta.com/) and [OneLogin](https://www.onelogin.com/), with support for additional identity providers on the way.

Single sign-on is available to customers on our enterprise plans. If you're interested in learning more about our enterprise plans, contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com?Subject=Single+sign-on).


### Behind the curtain


[Alexis](https://blog.launchdarkly.com/author/alexisgeorges/) and I collaborated on the single sign-on feature. The very first step we took was creating a feature flag for SSO in LaunchDarkly. With our feature flag seatbelt on, we didn't need to maintain a long-running branch for the feature, which meant we thankfully didn't have to suffer from massive merge conflicts. Every optional change that could be hidden behind that feature flag could be released incrementally and without extensive manual QA review.

When we demonstrated the feature in progress to a customer, we didn't need to use a staging system; we could demo on production because the feature was hidden behind a feature flag. When we were ready for the feature to be beta-tested, it was very easy to enable it for one customer and then another. The SSO feature flag remains today, and now our sales team uses the flag to enable the feature for their customers.
