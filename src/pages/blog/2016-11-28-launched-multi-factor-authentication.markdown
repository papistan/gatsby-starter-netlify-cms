---
author: justinucd
comments: false
date: 2016-11-28 19:34:27+00:00
layout: post
link: https://launchdarkly.com/blog/launched-multi-factor-authentication/
slug: launched-multi-factor-authentication
title: 'Launched: Multi-factor authentication'
wordpress_id: 1218
categories:
- Product Updates
tags:
- mfa
- multi-factor authentication
- security
---

Our customers’ security has always been a top priority at LaunchDarkly. We’re excited to announce support for [multi-factor authentication (MFA)](http://docs.launchdarkly.com/docs/multi-factor-authentication), which requires a second login verification step in addition to an account password.

[![LaunchDarkly multi factor authentication (MFA) feature flags feature toggle security](https://blog.launchdarkly.com/wp-content/uploads/2016/11/ld_mfa.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/11/ld_mfa.png)

MFA works by requiring users to enter a verification passcode from any free [authenticator ](https://support.google.com/accounts/answer/1066447?hl=en)application installed on your mobile device. If someone ever gained unauthorized access to your account password, then that person would not be able to log in without the MFA passcode.

LaunchDarkly account administrators can require all newly invited team members to enable MFA during their initial onboarding. Administrators can also see which team members have MFA enabled and send a reminder email or recovery code to assist.

We strongly recommend that all LaunchDarkly users enable MFA for their account, and that administrators enforce MFA for their entire team. If you have any questions or feedback, we would love to hear from you at [support@launchdarkly.com](mailto:support@launchdarkly.com).
