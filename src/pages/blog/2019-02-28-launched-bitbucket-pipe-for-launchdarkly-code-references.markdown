---
author: sagarwal
comments: false
date: 2019-02-28 18:43:23+00:00
layout: post
link: https://launchdarkly.com/blog/launched-bitbucket-pipe-for-launchdarkly-code-references/
slug: launched-bitbucket-pipe-for-launchdarkly-code-references
title: 'Launched: Bitbucket Pipe for LaunchDarkly Code References'
wordpress_id: 193755
categories:
- Product Updates
tags:
- BitBucket
- code references
- git
---

We're proud to be a launch partner for [Bitbucket Pipes](https://bitbucket.org/blog/meet-bitbucket-pipes-30-ways-to-automate-your-ci-cd-pipeline?utm_source=launchdarkly&utm_medium=press-release&utm_campaign=bitbucket_bitbucket-pipes) with our new Code References feature.  Pairing Bitbucket Pipes' CI/CD capabilities with LaunchDarkly feature flags allows modern development teams and organizations to write and ship code at their own pace while still ensuring that customers and users get the best possible experience.

As we've grown, we wanted to make it easier for development teams to ensure that the code they're deploying is safely wrapped in feature flags when it's deployed and to help teams remove feature flags after a feature has been exposed to 100% of all users and customers. With Code References, it's easy to determine which files in your Git repositories reference your feature flags, and makes cleanup and removal of technical debt easy.

The `ld-find-code-refs` Bitbucket Pipe sends updated snippets back to LaunchDarkly every time you do a deploy.  By baking in Code References into your standard build and deployment workflows using Pipes, everyone on your team has the confidence that you've wrapped all new code in a flag when you deploy and that you've safely removed all feature flags when you've released a new feature to all customers and users.

Learn more about LaunchDarkly's Code References [here](https://docs.launchdarkly.com/v2.0/docs/git-code-references) and get more information on the LaunchDarkly Code References Bitbucket Pipe [here](https://docs.launchdarkly.com/v2.0/docs/bitbucket-pipes-coderefs).
