---
author: csavage
comments: false
date: 2019-08-19 16:35:51+00:00
layout: post
link: https://launchdarkly.com/blog/launched-flag-archive-workflow/
slug: launched-flag-archive-workflow
title: 'Launched: Flag Archive Workflow'
wordpress_id: 194198
categories:
- Product Updates
---

When it comes to feature flags, most teams want to remove them once they’ve completed the job. Keeping tidy dashboards and codebases are part of your best practices. At the same time, many teams don’t remove flags because it takes time and making a mistake can have a large impact.

The new [Flag Archive](https://docs.launchdarkly.com/docs/flag-archive-delete) workflow makes it easy to confidently remove unused flags. Clutter-free dashboards will help you more quickly find the place you need to be, and have higher confidence in what features are currently being managed by your flags.

You’ve probably gone back to clean up old flags before, but decided to do it later after remembering you need to double check the rollout states, default values in your code, and any flag prerequisites. Not to mention your team might have multiple production environments, and you’d have to manually click between each environment. Not enough time!

Now, LaunchDarkly does most of the work for you. We bring the most important flag information—from across whichever environments you need—into a single panel so you can quickly assess whether a flag is safe to remove without unintended consequences.

Let’s take a look at how it works.

When you select a flag to archive, the Archive panel will appear where you can select the environments that matter for your team.

[![archive panel in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-13-at-5.09.50-PM-1024x702.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-13-at-5.09.50-PM.png)

After selecting your production environments, LaunchDarkly will summarize your flag state across your chosen environments for you to review.

[![archive panel in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-15-at-2.32.16-PM.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-15-at-2.32.16-PM.png)

Safety first! Confirm the flag name before archiving.

[![archive panel in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-14-at-7.45.35-PM-1024x221.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-14-at-7.45.35-PM.png)

And, you can always review your archives to recreate a previous flag behavior or recall fond memories of a rollout well managed.

[![archive panel in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-14-at-7.43.26-PM-1024x557.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/08/Screen-Shot-2019-08-14-at-7.43.26-PM.png)

This workflow is only a piece of the puzzle. Looking to the future, LaunchDarkly will continue investing in ways to help you and your team make better informed decisions, faster. Keep an eye out for future announcements!

For more information contact [sales@launchdarkly.com](mailto:sales@launchdarkly.com) or start a free trial to try out LaunchDarkly today!
