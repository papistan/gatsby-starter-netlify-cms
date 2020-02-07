---
author: Kimh
comments: false
date: 2017-11-30 22:33:38+00:00
layout: post
link: https://launchdarkly.com/blog/launched-personal-access-tokens/
slug: launched-personal-access-tokens
title: 'Launched: Personal Access Tokens'
wordpress_id: 2102
categories:
- Product Updates
tags:
- personal access tokens
- security
- tokens
---

LaunchDarkly users can now create personal API access tokens. Anyone who uses our API in an automated fashion knows they must authenticate with an access token. Until recently, this meant there was one token for an entire organization or account. To meet the needs of larger teams as well as others leveraging the LaunchDarkly API we wanted to provide not only greater granularity in responsibility but also better accountability. In our original token model only admins had the ability to create and view tokens since they were afforded global access and control.


### **What exactly are they?**


Personal access tokens are an improvement on this process. Now every user can create their own access tokens for authenticated API access. Users can scope permissions, making it easier to create different tokens for different use cases. So, if API access tied to a particular account should only have read access, now you can scope the token appropriately. Also, built-in and custom roles can be assigned to access tokens in the same way that you give a team member a role. This means that the roles-based controls you put in place for the web application are extended fully to the API access on our platform as well.


### **Best Practices**


Now that personal access tokens are available, we recommend LaunchDarkly users migrate to using these instead of account-wide tokens. The old tokens will continue to function, but we also recommend deleting those for improved security. 

In terms of using the personal access tokens, we strongly suggest creating a new token for each use case and giving them the smallest number of permissions necessary to do its job. We are proponents of the [principle of least privilege](https://blog.launchdarkly.com/how-to-comply/) and security best practices that limit your risk. After all, our goal is to help you eliminate risk, not increase it. 

With personal access tokens teams can also more effectively manage accountability. With an [audit log](https://blog.launchdarkly.com/the-only-constant-in-modern-infrastructure-is-change/), admin no longer need to worry about figuring out who has done what with a single token. Now they can monitor all access tokens based on who created them. Tokens can never do more than the user who created them, and if the user’s permissions are downgraded, so are the token’s. When the only constant in modern infrastructure is change, it’s important to have visibility into who has done what and a durable record of when it was done.

You can read more about personal access tokens in the documentation [here](https://docs.launchdarkly.com/v2.0/docs/api-access-tokens). And if you have any comments, you can contact us here, or make comments [directly in the repository](https://github.com/launchdarkly/ld-openapi).
