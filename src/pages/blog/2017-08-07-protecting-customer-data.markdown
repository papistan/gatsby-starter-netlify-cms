---
author: Andrewb
comments: false
date: 2017-08-07 15:08:08+00:00
layout: post
link: https://launchdarkly.com/blog/protecting-customer-data/
published: false
slug: protecting-customer-data
title: Protecting customer data
wordpress_id: 1865
categories:
- DevOps
---

What does a new engineer do during their first week at a[SOC 2 Type 1 Compliant](https://blog.launchdarkly.com/launched-launchdarkly-soc-2-certification/) startup?  **Write code?**  Maybe._  _ **Deploy code?** Hopefully.  **Create accounts?** Certainly.  **Generate passwords?  **_Ad nauseam._

After creating my Clubhouse and Quip accounts, half the items I saw on my TODO lists were  about creating accounts on more services.  Also on my calendar was to attend training for one of LaunchDarkly's newest initiatives: [SOC 2 Type 1 Compliance.](https://blog.launchdarkly.com/launched-launchdarkly-soc-2-certification/)

At LaunchDarkly, not only do we maintain mission critical services for our customers (feature flags!) we also store sensitive data about our customers' clients as part of our analytics features.  It is essential to our business that we protect not only access to control over customer application behavior but to _all_ client data we store on behalf of our customers.

After our security training, each member of my incoming class made a commitment to:



 	
  * Create a unique password for every service.  (Use a password generator and a password manager!)

 	
  * Enable 2-factor authentication for every service that offers it.

 	
  * Avoid sharing passwords with team members (to keep a precise audit trail).

 	
  * Restrict browser plugins to the minimum necessary to do your job.  Those plugins can read your data.

 	
  * Secure your laptop with FileVault and lock screens.

 	
  * Limit connected applications with access to gmail, github and other accounts.

 	
  * Secure customer data (obfuscated links don't cut it).


These are all great practices even if your business doesn't need SOC 2 Type 1 certification. Now to deploy some code (if I can just remember my ssh key...).
