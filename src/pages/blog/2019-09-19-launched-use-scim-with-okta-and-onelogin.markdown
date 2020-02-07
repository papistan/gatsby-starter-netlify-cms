---
author: mcho
comments: false
date: 2019-09-19 16:35:09+00:00
layout: post
link: https://launchdarkly.com/blog/launched-use-scim-with-okta-and-onelogin/
slug: launched-use-scim-with-okta-and-onelogin
title: 'Launched: Use SCIM with Okta and OneLogin'
wordpress_id: 194319
categories:
- Product Updates
tags:
- custom roles
- Okta
- onelogin
- SCIM
---

We're happy to announce SCIM support for two identity providers. This will give admins the ability to automatically create, manage, and remove seats when users change teams while maintaining the ability for users to log in securely and easily.


### What's New


We've had larger and more diverse teams adopt feature flagging, and we're excited! So it's even more important that we provide secure standards for user management. We've developed a SCIM connector to let you provision, manage, and deprovision users from a central identity provider (IdP).


### What's SCIM?


SCIM is a standard that lets applications control user data and profiles from a central IdP. If you're managing all of your org's users, roles, and services from one IdP or user directory, SCIM lets you do so with less work and in a more secure way.

Without SCIM, most organizations with a large and growing stack of microservices provision users in ad-hoc ways. They don't have the ability to automatically deprovision users instantly as they leave teams. This creates a security hole where former users could access restricted services even after they've left an organization. We're adding support for SCIM to improve your organization's security by letting you manage users quickly and easily from one place.


### How can I use this?





 	
  * Configure and use **Okta** or **OneLogin** to provision users for LaunchDarkly

 	
  * Manage LaunchDarkly Custom Roles for your existing IdP groups, as well as individuals

 	
  * Immediately deprovision users from your IdP when necessary




### Help us build a better experience for you and your teams!


We're thinking about how to improve your experience managing teams. [Tell us directly](https://airtable.com/shrpIQHdxCcXbzSGK) using this form - help us understand what you want to see next to manage your teams and users, whether that's Teams in LaunchDarkly, usage reporting, group dashboards, administrative tools, or something else entirely.

Read more in our [OneLogin](https://docs.launchdarkly.com/docs/onelogin) and [Okta](https://docs.launchdarkly.com/docs/okta) docs, and contact your account executives or support@[launchdarkly.com](http://launchdarkly.com/) if you would like to see other platforms supported.
