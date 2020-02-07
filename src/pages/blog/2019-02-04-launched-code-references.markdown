---
author: sagarwal
comments: false
date: 2019-02-04 20:17:47+00:00
layout: post
link: https://launchdarkly.com/blog/launched-code-references/
slug: launched-code-references
title: 'Launched: Code References'
wordpress_id: 193705
categories:
- Product Updates
tags:
- BitBucket
- CircleCI
- code references
- feature flags
- feature management
- github
- github actions
- technical debt
---

As your organization becomes more adept at using LaunchDarkly to safely deploy new code at a faster pace, your code can have many feature flags. When you release a feature to 100% of your users, it's often time to remove that flag from your code. Today, we're releasing a new feature called Code References that surfaces all instances of a LaunchDarkly feature flag in your code to make this process easy.

With Code References, you can ensure that you've wrapped the correct code with the appropriate flag and identify all places a flag lives in your code when it's time to remove it. We've built Code References by utilizing a utility called `ld-find-code-refs` that is available as a Github Action, CircleCI Orb, and as a command-line utility—and because of this, LaunchDarkly does not have access to your source code. Code References works with any Git repository, hosted with any cloud provider or your on-premise Git server.

This `ld-find-code-refs` utility scans your deployed code and sends snippets back to LaunchDarkly so you can be sure that flags are where you expect them, and to give you confidence they're removed when no longer necessary. You'll see all of these Code References in the LaunchDarkly UI under a Code references tab for each flag. Code References can be set up per project, so you can use Code References on only the projects you want.

You can use the `ld-find-code-refs` Github Action, or CircleCI Orb to send updated snippets back to LaunchDarkly automatically every time you do a deploy. You can also choose to invoke it in your CLI anytime you wish. By baking Code References into your standard deployment workflows using Orbs, everyone on your team has the confidence that you've wrapped all new code in a flag when you deploy and that you've safely removed all feature flags when you've released a new feature to all customers and users.

Code References is in public beta and is available to all LaunchDarkly customers. Learn more about [LaunchDarkly's Code References here](https://docs.launchdarkly.com/v2.0/docs/git-code-references).
