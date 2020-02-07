---
author: justinucd
comments: false
date: 2017-04-04 18:42:25+00:00
layout: post
link: https://launchdarkly.com/blog/we-got-your-rbac/
slug: we-got-your-rbac
title: We got your RBAC
wordpress_id: 1488
categories:
- Feature Management
tags:
- access control
- custom roles
- feature flag management
- feature flags
- security
---

#### How LaunchDarkly gives teams granular access and security control for their feature flag management


Enterprise companies take security and privacy very seriously: risk must be mitigated, customer privacy must be protected, and software releases must be controlled.  Feature flags are essential tools to granularly control software releases, but with great power comes great responsibility.  When you have hundreds of stakeholders using a product, you need to make sure that every team member has the exact permissions they need: no more, no less.

Powerful tools demand powerful access controls.  This means that your demoing account executive should not be able to toggle off live production features unless they are explicitly allowed to enable for a customer.  Likewise, your developers should be able to use feature flags in their own environments, but might not have access to disable functionality that customers depend on. 


## Custom Roles


To make this a reality, LaunchDarkly has built an extremely powerful and granular access control system that we call [custom roles](http://docs.launchdarkly.com/v2.0/docs/custom-roles).

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/04/access_auditlog-1.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2017/04/access_auditlog-1.jpg)

Custom roles let you control access for every team member and every feature in LaunchDarkly, from a particular flag’s percentage rollout to the ability to toggle a flag on or off.  You can create a role using our custom roles builder.

Here are some possible custom roles:



 	
  * Lock your production environment down to a small set of trusted users

 	
  * Distinguish infrastructure-level feature flags (controlled by your devOps team) from experiments (controlled by product management or marketing)

 	
  * Allow QA members to control feature flags on designated QA environments only

 	
  * Allow your designers to add users to betas

 	
  * Allow sales to turn a feature “on” for a user




## Security


Equally essential for security is the ability to prevent nefarious access and brute force attacks.  Companies want to make sure that the platform controlling their feature releases conforms to security best practices.

As such, LaunchDarkly provides [multi-factor authentication](http://docs.launchdarkly.com/v2.0/docs/multi-factor-authentication) and [session control](http://docs.launchdarkly.com/v2.0/docs/managing-sessions) for all customers.  Multi-factor authentication (MFA) improves the security of your account by requiring a second verification step in addition to your password to login. In LaunchDarkly, you can enable multi-factor authentication for your team’s account, which requires you to enter a verification passcode from a free authenticator application you install on your mobile device.  You can also require all team members to enable MFA before accessing their accounts.

Moreover, LaunchDarkly’s session control offers administrators a set of controls to manage how long users stay logged in to their account, and how often they need to re-authenticate.  This allows admins to take proactive measures when an account is compromised or a laptop is lost, providing full control over LaunchDarkly account access.


## Summary


Feature flagging is increasingly becoming central to a company’s software development and release lifecycles.  As part of a company’s critical infrastructure, feature flag management platforms must have enterprise-grade security to ensure that customer data is safe and that every team member has the exact access they need.
