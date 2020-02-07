---
author: johnkodumal
comments: false
date: 2018-10-17 12:17:04+00:00
layout: post
link: https://launchdarkly.com/blog/github-actions-controlled-with-launchdarkly/
slug: github-actions-controlled-with-launchdarkly
title: GitHub Actions Controlled with LaunchDarkly
wordpress_id: 193455
categories:
- Product Updates
tags:
- automated workflows
- development workflows
- feature flagging
- feature management
- github
- github actions
- technical debt
---

At GitHub Universe this week, GitHub announced a new, groundbreaking capability for repositories: GitHub Actions.


GitHub Actions allow you to implement custom logic without having to create an [app](https://developer.github.com/apps) to perform the task you need. You can combine GitHub Actions to [create workflows](https://developer.github.com/actions/creating-workflows/) using an action defined in your repository, a public repository on GitHub, or a published Docker container image.




With GitHub Actions, workflows are defined in your repository and triggered by events on GitHub.




For example, an action can publish [npm](https://www.npmjs.com/) modules, send SMS alerts when urgent issues are created, or deploy production ready code.


[![Screenshot of GitHub Actions visual editor](https://blog.launchdarkly.com/wp-content/uploads/2018/10/actions-create-labeled-action-1024x506.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/actions-create-labeled-action.png)

(Example of GitHub Actions visual editor)

In anticipation of the launch, GitHub asked us to use LaunchDarkly showcase the power of GitHub Actions. We were excited to see how we could use GitHub Actions to automate workflows our customers use on a regular basis. Just as GitHub helps developers use Git effectively, we love helping customers use feature flags effectively.


### Simple Workflows


We set out to make it easier for developers to review Pull Requests for new features that are using feature flags. We started by creating a GitHub Action workflow on a repository. The simple case allowed us to trigger a deploy to a staging environment when a pull request (PR) was created. Though this is not anything new, it took practically no time to setup and was managed entirely through GitHub. No additional tools required.

[![Screenshot of a LaunchDarkly GitHub Actions workflow](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-5-4-1024x640.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-5-4.png)

Of course, the whole point of developing code with feature flags is to reduce the impact for folks that don't need to see the new features. In the case of a PR automating a deploy to staging, this likely means hiding this feature from everyone except the folks that need to review the PR.  GitHub Actions allowed us to build a workflow to do just that.

We were easily able to create an Action that is triggered when a reviewer is added to a PR. The workflow will turn on the feature flag for every reviewer that is added to the PR, ensuring they will have access to the feature to conduct their review.

[![Screenshot of LaunchDarkly GitHub Actions workflow](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-5-56-1024x640.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-5-56.png)

[![Screenshot of adding live flag in LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-6-18-1024x640.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-6-18.png)


### Adding Flags


Following through on the scenario above, we realized that there were times we wanted to have greater control over the GitHub Actions workflow. For example in the scenario given we realized that in some cases we might not want the deployment go to a staging environment, instead we might want to deploy to a QA environment first to allow for further testing and feedback.

We realized that we could use LaunchDarkly feature flags to control the behavior of the workflows in GitHub. We created a feature flag for the GitHub Action itself. When the workflow runs we can evaluate a feature flag in LaunchDarkly. When you want to change the deployment destination you can just update the flag, without having to change the workflow. And thanks to our [streaming architecture](https://launchdarkly.com/blog/designing-for-failure-to-avoid-disaster/), the changes will be picked-up by GitHub in 200ms or less.

[![Screenshot of GitHub Actions visual editor ](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_14-32-28-1024x640.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_14-32-28.png)

[![Screenshot of LaunchDarkly dashboard auto-deploy to environments](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-7-1-1024x640.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-7-1.png)

With GitHub Actions and LaunchDarkly, you get all the automation you want for your development workflows, with all the control you need through the use of feature flags.


### One More Thing...


The more feature flags you create, they more they accumulate over time. It's a good idea to clean up flags that are no longer in use. However, often the challenge is remembering where a particular flag was used – and this can be particularly difficult for flags that are in multiple locations.

Teams that use LaunchDarkly for managing hundreds or even thousands of flags have asked for some way to keep track of all the flag locations. Thanks to GitHub Actions, we were able to build this highly requested feature. In our new Code tab, developers can now see _everywhere_ a feature flag is used in their repositories.

[![Screenshot of LaunchDarkly dashboard show live tiles](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-7-42-1024x640.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/10/image2018-10-15_23-7-42.png)


### What To Do Now?


If you'd like to give this a spin, sign-up for the [GitHub Actions beta](https://github.com/features/actions) and let us know if you like to be added to the ["Flag Locations" beta](mailto:beta@launchdarkly.com?subject=Beta - GitHub Flag Locations). We can't wait to see what you create.
