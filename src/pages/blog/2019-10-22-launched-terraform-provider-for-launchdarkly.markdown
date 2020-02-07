---
author: hbarrow
comments: false
date: 2019-10-22 14:18:11+00:00
layout: post
link: https://launchdarkly.com/blog/launched-terraform-provider-for-launchdarkly/
slug: launched-terraform-provider-for-launchdarkly
title: 'Launched: Terraform Provider for LaunchDarkly'
wordpress_id: 194408
categories:
- Product Updates
tags:
- cloud infrastructure
- infrastructure
- infrastructure management
- terraform
---

We are pleased to announce the launch of our official LaunchDarkly Terraform provider. This allows development teams to create and manage LaunchDarkly _resources_ such as projects, environments, feature flags, and more by using Terraform's declarative configuration language.


### About Terraform providers


[Terraform](https://www.terraform.io/) by [HashiCorp](https://www.hashicorp.com/) is an open-source tool for managing cloud infrastructure and resources using a high-level configuration syntax. Many of LaunchDarkly's customers enjoy the benefits of Terraform's "infrastructure as code" paradigm to provision version-controlled, reproducible cloud resources by leveraging official providers from AWS, Cloudflare, PagerDuty, Github, and [many more](https://www.terraform.io/docs/providers/index.html). LaunchDarkly plays a vital role in helping these teams manage their infrastructure. With this Terraform provider, teams can begin configuring LaunchDarkly resources right alongside the rest of their infrastructure stack.

[caption id="attachment_194411" align="aligncenter" width="514"][![Terraform-config-file](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-14_16-50-54.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/10/image2019-10-14_16-50-54.png) Sample config file.[/caption]


### Benefits of LaunchDarkly's Terraform provider


Our Terraform provider empowers teams to simplify the process of managing LaunchDarkly resources. Here are a few example use cases:



 	
  * Rapidly provision environments for a new project with a set of commonly used permanent feature flags

 	
  * Open a pull request to modify user segment groups and let [Terraform Cloud](https://www.terraform.io/docs/cloud/index.html) apply the changes

 	
  * Keep flag definitions in the same repository as application code, making flags cleanup a breeze

 	
  * Easily sync complex targeting rules for all flags across several environments

 	
  * Create and apply complex custom roles across your organization


The goal of this provider is not to make you choose between using the LaunchDarkly user interface (UI) or the Terraform provider. Instead, we encourage you to identify tasks that can be automated and standardized by using the Terraform provider and then use the LaunchDarkly web application for everything else.

_**Bonus suggestion:** You can tag Terraform-managed resources with a `terraform` tag and use [custom roles](https://docs.launchdarkly.com/docs/custom-roles) to prevent team members from modifying those resources via the LaunchDarkly UI._


### How to get started with the Terraform provider


To get started with LaunchDarkly's Terraform provider, check out our [documentation](https://docs.launchdarkly.com/docs/terraform). We are excited to learn about how you are using Terraform for LaunchDarkly and are committed to making your experience a good one. If you have any questions or comments, please reach out to [feedback@launchdarkly.com](mailto:feedback@launchdarkly.com).

For examples showcasing the benefits of LaunchDarkly's Terraform provider, read our in-depth ["Managing Feature Flags with Terraform"](https://launchdarkly.com/blog/managing-feature-flags-with-terraform/) post.
