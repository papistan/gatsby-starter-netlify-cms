---
author: justinucd
comments: false
date: 2016-01-19 01:02:08+00:00
layout: post
link: https://launchdarkly.com/blog/launched-custom-roles/
slug: launched-custom-roles
title: 'Launched: Custom Roles'
wordpress_id: 333
categories:
- Product Updates
tags:
- Amazon
- custome roles
- Enterprise
- IAM
- permissions
- policies
---

##### **New permission system launches with custom roles, providing teams with fine-grained access control to everything in LaunchDarkly.**





* * *



We're happy to announce the beta launch of [Custom Roles](http://docs.launchdarkly.com/v1.0/docs/custom-roles)!**  **You will now be able to customize permissions for each of your team members.  This system enhances LaunchDarkly's basic permission system by providing comprehensive and fine-grained access control for our enterprise customers.

<!-- more -->One of the most common requests for us at LaunchDarkly has been the ability to lock down access to feature flags in production. Over time, though, we started hearing other needs:



 	
  * "My ops team should be able to access infrastructure flags, but my product managers need to manage experiments"

 	
  * "My QA team should have full control over my test environments, but they don't need to create feature flags"


We realized that we needed to build an access control system flexible enough to work with a team's desired workflow, but simple to administer and use. That's why we built a new custom roles feature, inspired by[ IAM, Amazon's enterprise-grade access policy engine](https://aws.amazon.com/iam/).

**The Power of Custom Roles**



 	
  * Lock your production environment down to a small set of trusted users

 	
  * Distinguish infrastructure-level feature flags (controlled by your DevOps team) from experiments (controlled by product management or marketing)

 	
  * Allow QA members to control feature flags on designated QA environments only


**Features**



 	
  * ****[Basic Permission System](https://blog.launchdarkly.com/launched-account-permissions/)****

 	
    * Global access control levels for team members based on a set of built-in roles

 	
    * Only supports Reader, Writer, Admin, and Owner




 	
  * ****[Enterprise Permission System with Custom Roles](http://docs.launchdarkly.com/v1.0/docs/custom-roles) (NEW) ****

 	
    * Inspired by [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/)

 	
    * Create custom policies for fine-grained control over everything in LaunchDarkly -- from feature flags to goals, environments, and teams

 	
    * Create unlimited custom roles for complete access control

 	
    * Assign one or more custom roles to each team member, or use any of the features in the basic permissions system

 	
    * _Available only for enterprise customers (Contact sales@launchdarkly.com to learn more)_







**How It Works**

**- Your teammates can now have both basic and custom roles.  **In this example, "Sasha Baker" has the roles "QA Team" and "Restricted".

[![Feature Flags Custom Roles LaunchDarkly](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles3.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles3.png)



**- Click on any teammate to manage his or her roles.  **In this example, "Sasha Baker" has been assigned the custom roles "QA Team" and "Restricted".  You have the option of assigning global roles (Reader, Writer, Admin) or custom roles (Ops Team, QA Team, Restricted + any other roles you create).

[![customroles_edit](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles_edit.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles_edit.png)



**- Click the "Roles" tab to view your custom roles or create new ones.  **You may create as many roles as you like.

[![LaunchDarkly Feature Flags Custom Roles](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles_list.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles_list.png)



**- Add a custom policy to your role.** See our [documentation](http://docs.launchdarkly.com/v1.0/docs/custom-roles) for details.

[![LaunchDarkly Feature Flags Custom Roles Policy](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles_policy.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/01/customroles_policy.png)

**Getting Started**



 	
  * _Custom roles is in beta and only available to enterprise customers._**  **If you're interested in access to the beta, contact us at **team@launchdarkly.com**

 	
  * Our [documentation](http://docs.launchdarkly.com/v1.0/docs/custom-roles) provides detailed instructions on implementing custom roles for your team



