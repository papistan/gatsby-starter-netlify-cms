---
author: justinucd
comments: false
date: 2016-05-23 17:35:50+00:00
layout: post
link: https://launchdarkly.com/blog/launched-projects/
slug: launched-projects
title: 'Launched: Projects'
wordpress_id: 841
categories:
- Product Updates
tags:
- Environments
- LaunchDarkly
- New Feature
- Projects
---

#### **Overview**


We’re happy to announce the launch of [Projects](http://docs.launchdarkly.com/v1.0/docs/projects) for all LaunchDarkly customers. Projects allow you to manage multiple software projects under one LaunchDarkly account.  For example, you can create one project called _Mobile App_ and another project called _Web App_. Each project will have its own unique set of [environments](http://docs.launchdarkly.com/docs/environments) and feature flags.  By default, all team members in your LaunchDarkly account will have access to every project within that account.  Please see our [documentation](http://docs.launchdarkly.com/v1.0/docs/projects) for more information.


#### **Benefits**


With projects, teams get comprehensive feature flag management control across multiple different software applications. You can now:



 	
  * Manage all of your software projects under one LaunchDarkly account

 	
  * Keep your "Mobile App" feature flags separate from your "Web App" feature flags

 	
  * Use [custom roles](http://docs.launchdarkly.com/docs/custom-roles) to assign team members to different projects

 	
  * Create multiple development [environments](http://docs.launchdarkly.com/docs/environments) within each project (e.g. local, QA, staging, and production).




#### ![LaunchDarkly Projects Feature Flags Feature Toggles Feature Flag Management](https://blog.launchdarkly.com/wp-content/uploads/2016/05/Projects.jpg)




#### **Projects**




When you first create your LaunchDarkly account, you will start with a _Default_ project.  You can then create additional projects for each of your software applications. 

[![LaunchDarkly Projects Dashboard](https://blog.launchdarkly.com/wp-content/uploads/2016/05/projects_blur.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/05/projects_blur.jpg)


_A LaunchDarkly account showing two projects “Mobile App” and “Web App”, each with its own “Production” and “Test” environments._




----




[![LaunchDarkly Create Projects](https://blog.launchdarkly.com/wp-content/uploads/2016/05/createproj_blur.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/05/createproj_blur.jpg)_Creating a new project is easy.  Name a project and you’re ready to go._


Within your projects, you can create multiple [environments](http://docs.launchdarkly.com/docs/environments). Environments allow you to manage your feature flags throughout your entire development lifecycle — from local development to QA, staging, and production.  These environments are scoped to the project. Please note that all projects must have at least one environment.


[![LaunchDarkly Projects and Environments](https://blog.launchdarkly.com/wp-content/uploads/2016/05/projenv_blur.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2016/05/projenv_blur.jpg)_Easily create multiple development environments for each project.  __In this example, we are adding a “Local Development” environment to our “Mobile App” project._



