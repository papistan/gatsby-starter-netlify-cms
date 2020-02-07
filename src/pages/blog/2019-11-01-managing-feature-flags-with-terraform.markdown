---
author: ygrahame
comments: false
date: 2019-11-01 21:40:28+00:00
layout: post
link: https://launchdarkly.com/blog/managing-feature-flags-with-terraform/
slug: managing-feature-flags-with-terraform
title: Managing Feature Flags with Terraform
wordpress_id: 194464
categories:
- DevOps
tags:
- cloud infrastructure
- infrastructure
- infrastructure management
- terraform
---

Two weeks ago, we launched the [LaunchDarkly Terraform provider](https://launchdarkly.com/blog/launched-terraform-provider-for-launchdarkly/). By using Terraform to manage LaunchDarkly resources, you can eliminate much of the pain and busywork in rolling out changes across your teams and infrastructure. In this post, I’ll explain what Terraform is and the value in using it to manage feature flags. I’ll also provide a couple of in-depth examples that demonstrate different ways to use the provider.


### Why Terraform?


Complexity is often unavoidable in modern software development. Whether you’re building software in the cloud, constructing services with microservices, looking to create a unified experience across platforms with a multi-tiers application, or just trying to provide a globally available service – your software gets complicated… fast.

Much of the complexity comes from the variety of cloud services you may be using to support your software. These services solve many problems when building your app, but they also add others: how are you going to provision and manage all these different resources? Logging into a console and clicking buttons doesn't seem so bad at first, but the busy work increases with each service or resource that you add. It gets even worse when you have to replicate the set of resources to make another environment, such as staging and test environments, to go alongside production. What if you need to make a change across a hundred storage buckets? Worse, what if you have multiple team members all trying to make changes, and suddenly one of them needs to roll a change back?

Terraform can take care of all of these problems. That’s why it’s so popular.


### The value of Terraform


Terraform can both unify your infrastructure management and simplify the change process:



 	
  * **Manage through one tool:** You can stop jumping around different control consoles to manage infrastructure resources. Whichever cloud services you're using, the chances are that Terraform can handle them for you. The Terraform extensions for talking to specific services are called _providers_, and there are literally hundreds of them. (If you can't see the one you need in the [officially-maintained list](https://www.terraform.io/docs/providers/index.html), check the [community](https://www.terraform.io/docs/providers/type/community-index.html).)

 	
  * **Work on the design, and let Terraform worry about the process:** Terraform has enough built-in smarts about cloud services that it doesn't need to be told how to deploy them. Use **HashiCorp Configuration Language (HCL)** to define what you want the end result to be and Terraform can work out a plan for getting there. Want to check that plan before running it? Use the plan command, and Terraform will show you all the changes it intends to make.

 	
  * **Define resources in a single place and language (a text file written in HCL):** It doesn't matter how many different cloud services and providers you use; they can all be grouped together in the scheme that's most useful to you. Store and version the text file(s) in your code repository along with all your other code.

 	
  * **An optional cloud service for running plans and tracking state:** Terraform started as an open source tool to be installed and run locally, and that’s how most teams use it. To make it easier, [HashiCorp recently released Terraform Cloud](https://www.hashicorp.com/blog/announcing-terraform-cloud/). You don’t need to install anything to use it, and it’s free for small teams.


Of all those features, it’s the simplest one - defining resources in text files - that’s the most effective, because it also simplifies the change process.


### Infrastructure As Code


Given the fragility of service infrastructure, it’s important to have consistent processes around creating and changing configurations. Modifications should be reviewed before they’re applied, then tracked in a complete history log, which also makes it easy to rollback if something goes wrong. In other words, infrastructure needs the kind of workflow we already have with code. But you can’t do that when you’re managing infrastructure with manual clicks and one-off commands in consoles.

By moving your infrastructure configuration into text files, Terraform doesn’t just let you manage it like code. If you store those files in the project’s code repo, Terraform also lets you commit infrastructure changes in sync with the code changes that need them. Your continuous integration can test code and configuration together. This approach is known as [Infrastructure As Code](https://www.martinfowler.com/bliki/InfrastructureAsCode.html).

For many engineering teams, using Terraform has been a remarkable way to manage their complexity. Now, with our new Terraform provider, they can bundle the configuration of a new feature flag with the code and infrastructure that uses it, all in a single commit.


### Managing LaunchDarkly resources with Terraform


Feature flags are vital parts of your infrastructure. At LaunchDarkly, we eat our own [dog food](https://deviq.com/dogfooding/) and heavily flag everything we build and release. Given that a single flag can include a complex set of rules and other details, it makes sense to have that configuration reviewed in a similar way to how we review code.

It's not just about the flags themselves. Your LaunchDarkly setup can include [Projects](https://docs.launchdarkly.com/docs/projects), [Environments](https://docs.launchdarkly.com/docs/environments), and [Segments](https://docs.launchdarkly.com/docs/segmenting-users). There can be [Custom Roles](https://docs.launchdarkly.com/docs/custom-roles) allocated to different [Team Members](https://docs.launchdarkly.com/docs/teams). The LaunchDarkly provider for Terraform allows you to manage as many of these in HCL as you like.

But the most important point here is: **you don’t have to manage everything the same way.** There may be areas where you value agility over consistency, for example. In such a case, it may be better to let certain team members manage the resources for those areas through the UI.

In the following examples, you’ll see some of the LaunchDarkly provider’s features. You’ll also see options for maintaining strict workflow around some resources, and looser control over others.


### Example 1: Per-developer Environments, without flag details


You don't need to store individual flag details in Terraform to use our Terraform provider effectively. To demonstrate that, let's talk about a common scenario for engineering teams collaborating on a software product: live development instances.

Each developer on the team should have their own running instance of the product with which they can experiment. Each instance requires its own set of resources, such as databases, static files, worker processes, and feature flags. The instance is created together with its resources, and given a unique identifier. This identifier includes the name of the developer for whom it was created.

I’ll create a Terraform configuration for these instances and their resources. As I said earlier, one of Terraform's benefits is that it doesn’t force you to specify how these instances should be created, just what the end result should be. In my case, I want each developer’s instance to have an identical set of resources. So I’ll start with the list of developer names, declared as a [local value](https://www.terraform.io/docs/configuration/locals.html):

    
    locals {
      developers = [“frankie”, “stony”, “cleo”, “tt”]
    }


This is followed by a bunch of [resource blocks](https://www.terraform.io/docs/configuration/resources.html), each one representing a different component of the instance. In this example, the resources we care about are the [LaunchDarkly Environments](https://docs.launchdarkly.com/docs/environments). But Environments have to be part of a [LaunchDarkly Project](https://docs.launchdarkly.com/docs/projects), so I create that first, using the [launchdarkly_project](https://www.terraform.io/docs/providers/launchdarkly/r/project.html) resource:

    
    resource "launchdarkly_project" "downtown" {
      key  = "downtown"
      name = "Downtown Bank project"
    }


I want one LaunchDarkly Environment for each developer, and thanks to the [new loop constructs in Terraform 0.12](https://www.thegreatcodeadventure.com/building-dynamic-outputs-with-terraform-for_each-for-and-zipmap/#building-dynamic-resources-with-for_each), hardly any extra code is needed. Here's what the [launchdarkly_environment](https://www.terraform.io/docs/providers/launchdarkly/r/environment.html) resource block looks like:

    
    resource "launchdarkly_environment" "downtown" {
      for_each    = toset(local.developers)
      key         = "${each.value}-dev"
      name        = "${title(each.value)} dev env"
      color       = substr(md5(each.value), 0, 6)
      project_key = launchdarkly_project.downtown.key
    }


By embedding the developer's name into the key and name properties, I ensure that each Environment is named usefully and uniquely. I’ve even generated a different color for each Environment by calculating the [MD5 hash](https://www.makeuseof.com/tag/md5-hash-stuff-means-technology-explained/) of the developer name and grabbing the first six hexadecimal digits. (Note: given the randomness in the process, we make no guarantees about the color's suitability to your overall aesthetics. [YMMV](https://www.lifewire.com/what-is-ymmv-2483722).)

As I mentioned at the start, this works even if you have no individual flag details stored in Terraform. New flags can be created through the LaunchDarkly UI, and they'll be automatically included in every new Environment created for that Project. But you can manage your flags in Terraform as well! Our next example shows how you might do that.


### Example 2: Managing and protecting flags without changing their state


If some flags are particularly important, it makes sense to manage them through the same workflow as the code that relies on them. (This is the _Infrastructure As Code_ approach I discussed above.) In this example, I:



 	
  * Write HCL code to create a new flag

 	
  * Validate the Terraform syntax and actions automatically, thanks to Terraform Cloud’s integration with my code pipeline

 	
  * Ensure that the Terraform definition stays correct by preventing change through other interfaces


I’ll use a real product example for this one: adding a feature to our Slack app. I want to [unfurl](https://api.slack.com/docs/message-link-unfurling) the links that the app posts to Slack. As always with new features, I start with a feature flag in the “Slack App” LaunchDarkly Project. This time, I define the flag in Terraform:

    
    resource "launchdarkly_project" "slack" {
      key  = "slack-app"
      name = "Slack App"
      tags = ["slack"] # LaunchDarkly tags
    }
    
    data "launchdarkly_team_member" "yoz" {
      email = "yoz@launchdarkly.com"
    }
    
    resource "launchdarkly_feature_flag" "unfurl_links" {
      project_key   = launchdarkly_project.slack.key
      name          = "Unfurl Links"
      key           = "unfurl-links"
      description   = "whether or not to unfurl links"
      tags          = ["terraform-managed"]
      maintainer_id = data.launchdarkly_team_member.yoz.id
    
      variation_type = "boolean"
      variations {
        value = true
      }
      variations {
        value = false
      }
    }


I’ve defined the base flag configuration, but not its per-Environment states such as targeting or evaluation rules. Those are managed using a different resource: [launchdarkly_feature_flag_environment](https://www.terraform.io/docs/providers/launchdarkly/r/feature_flag_environment.html). Since I’m not managing that kind of resource through Terraform, I know that I can change the flag’s definition in code without affecting its state in each Environment.

I’ve also added a maintainer_id attribute to the flag, pointing at my LaunchDarkly user account. This will show up in the LaunchDarkly user interface, telling other members of my team that I’m responsible for this flag:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/11/maintainer.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/11/maintainer.png)

In the meantime, I can apply this Terraform change and make the flag available across Environments. But before we do that – have we got the syntax right? And even if we do, is this code going to do the right thing?

The good news is that we can answer those questions automatically.


### Automated review with Terraform Cloud


HashiCorp’s new Terraform Cloud has lots of nifty features, but my favourite is the way it analyzes and plans all your configuration changes as part of a code review process. With a few clicks you can integrate it with your GitHub repo. After that, all new pull requests will be checked for Terraform changes, and those changes will be run through the terraform plan command.

So, I’ll make a pull request on GitHub with my Terraform code changes. The pull request triggers the various continuous integration services, which now include Terraform Cloud:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/11/github.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/11/github.png)

Looks like all the tests have passed! But I still want to be certain of the changes that Terraform will make when my code is applied. So, I click the “Details” link to see the operations that Terraform Cloud has planned:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/11/tfcloud-run.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/11/tfcloud-run.png)

Scrolling through that plan, everything looks good. When this pull request is merged into the master branch, Terraform Cloud will apply it automatically, creating the LaunchDarkly Project and the “unfurl_links” feature flag within it. It will also create two Environments for the Project: Production and Test.


### Protecting Terraform-defined flags


Now that the flag’s core configuration is controlled through Terraform, I want to ensure that it’s not modified by other means - such as through the LaunchDarkly web interface. Our [Custom Roles](https://docs.launchdarkly.com/docs/custom-roles) feature is useful here:



 	
  1. Create a dedicated “terraform” user account in LaunchDarkly, which Terraform Cloud will use to perform all LaunchDarkly actions. This ensures that Terraform actions aren’t dependent on an individual team member’s LaunchDarkly account - rather, this is a dedicated account which belongs to the team as a whole.

 	
  2. Move all the other team member accounts into a new Custom Role which can’t modify certain attributes of Terraform-controlled resources. To make it easier to specify which resources these are, use a tag; the example above adds the terraform-managed tag to the new flag.


For in-depth information on setting up Custom Roles, look at [the documentation](https://docs.launchdarkly.com/docs/custom-roles).


### The missing example


We're near the end of this blog post, and so far I've talked entirely about using Terraform to control LaunchDarkly resources. But this isn't the way that LaunchDarkly usually integrates with code: namely, using feature flag values to choose which instructions to execute. Some readers may be wondering: can I use LaunchDarkly to control optional features in my HCL code?

The answer is: not yet, because we're not sure whether it’s a good idea. The overriding philosophy of Terraform is that plan runs should be **deterministic**. In other words, well-written Terraform code should be unambiguous about what it's going to do, and it should always produce the same end state. Feature flags are an external factor which change the result, and can't be seen from the code.

But there are also arguments in favor of using feature flags and other controls in HCL files. Firstly, the language supports it in multiple ways, such as external Data Sources and explicit branch instructions. Secondly, there are already [multiple examples](https://www.linkedin.com/pulse/using-feature-toggles-recover-ec2-server-terraform-bruce-dominguez) of Terraform users demonstrating ways to implement feature flags, so clearly there’s some demand for the latter.

Finally, as always with process philosophies, there may be room for flexibility. For example, we tend to want far stricter processes with production environments than developer environments. An ops team can use feature flags to delegate tightly-defined areas of control to developers, who can use those flags to tweak aspects of their developer instances (e.g., which git branch to deploy). The value of that delegation may be seen as a worthwhile trade-off when compared to continual support requests.

In researching this blog post, I've come across a variety of opinions on this topic but surprisingly little in-depth discussion. I'm interested to hear yours, so [I’ve started a Twitter thread here](https://twitter.com/yoz/status/1190325686457626624). (I welcome [feedback through email](mailto:feedback@launchdarkly.com) too!)


### Summary


Terraform is a remarkably powerful tool when used correctly. It provides a centralized change control process for infrastructure, thus helping a DevOps – or just plain ops – team to work together without stepping on each other’s toes. It can also remove tons of drudgery and toil from that work by taking care of many different resource-management tasks instantly.

Your feature flags are a vital part of application infrastructure and should be treated as such. The LaunchDarkly provider for Terraform brings us in line with the rest of your infrastructure control processes.

If I have you at all excited about using Terraform with LaunchDarkly, give it a try! You can [get started here](https://docs.launchdarkly.com/docs/terraform).
