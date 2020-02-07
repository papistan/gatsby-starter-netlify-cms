---
author: patrickkaeding
comments: false
date: 2016-04-26 15:46:50+00:00
layout: post
link: https://launchdarkly.com/blog/zombies-eating-your-aws-bill/
slug: zombies-eating-your-aws-bill
title: Zombies eating your AWS bill?
wordpress_id: 565
categories:
- DevOps
- Feature Management
tags:
- Amazon EC2
- Ansible
- AWS
- feature flag
- Lambda
- Python
---

The near-infinite elasticity of [Amazon's EC2](https://aws.amazon.com/ec2/) service is amazing. You can easily and cheaply spin up new instances whenever you need them. At LaunchDarkly, we provision new instances every time we deploy a new version of one of our services, which often happens multiple times in a day. We use [Ansible](https://www.ansible.com/) to orchestrate the provisioning and deploy process, which means that we have easily repeatable deploys, and no server is a [snowflake](http://martinfowler.com/bliki/SnowflakeServer.html). Using the ['cattle, not pets'](https://blog.engineyard.com/2014/pets-vs-cattle) mindset, we routinely create and destroy instances. The script basically does the following steps:






 	
  1. Provisions a fresh set of instances using a base AMI image that we have created

 	
  2. Pulls down the latest code and config files from [S3](https://aws.amazon.com/s3/) (which is where our [build server](https://circleci.com/) publishes to)

 	
  3. Runs a few smoke tests to be sure the app has started up

 	
  4. Swaps the load balancer configuration so the load balancers start sending traffic to the new instances

 	
  5. Waits for the old instances to finish processing any requests that they had received before the load balance switch

 	
  6. De-provisions the instances running the old version of the code


<!-- more -->


Note that the de-provisioning happens last. If something goes wrong in this process (the most common place for problems is that we forgot to update the production configuration file, so the app doesn't start properly, so the smoke tests in step 3 fail), then there will be instances left running that are not in the load balancer. Usually, we just fix the config and re-run the ansible script, and everything cleans up nicely, but sometimes some old instances can get left behind. Also, sometimes the provisioning in step 1 can get interrupted, resulting in the new instances just sitting there.




These problems are pretty rare, but they can be insidious because an instance happily sitting there doing nothing will not raise any alarms with our monitoring systems. They will just sit there racking up the bill.




**Get control of your zombie EC2 instances**




![Zombie Servers AWS](https://s3.amazonaws.com/uploads.hipchat.com/71570/1627772/DvRej31l283u0qv/eyes.min.gif)




In order to detect these 'zombie' instances, I wrote a [quick python script](https://github.com/launchdarkly/legendre) that hits each of our services through the load balancer to determine what the 'live' version is, and then traverses the EC2 API to inspect instance tags looking for instances that are running the wrong version of the code. It then publishes an alert to an [SNS](https://aws.amazon.com/sns/) topic. On our team, we have these notifications email the team and post a message in HipChat. We have this script run as a [Lambda](https://aws.amazon.com/lambda/) function hourly.




Since this might be useful to other teams too, I wanted to share it. Read on to see how you can set it up for your own environment. Please let us know if you find it useful!




**Assumptions**




This script makes use of [tags](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html) on the EC2 instances to determine if an instance is doing good work, or is languishing, undead. It also assumes you are using load balancers to find the 'live' instances (ELBs are fine for this, or really just any way to have a stable URL to discover the right instances). If these assumptions don't hold for your environment, you may need to make some additional tweaks.




The tags you need are:



<table cellpadding="0" cellspacing="0" class="t1" >
<tbody >
<tr >

<td class="td1" valign="middle" >


**Tag name**



</td>

<td class="td2" valign="middle" >


**Purpose**



</td>

<td class="td3" valign="middle" >


**Example**



</td>
</tr>
<tr >

<td class="td4" valign="middle" >


tier



</td>

<td class="td5" valign="middle" >


separate environments



</td>

<td class="td6" valign="middle" >


production, staging, etc



</td>
</tr>
<tr >

<td class="td4" valign="middle" >


app



</td>

<td class="td5" valign="middle" >


identify services



</td>

<td class="td6" valign="middle" >


frontend-app, backend-thing, other-backend-thing



</td>
</tr>
<tr >

<td class="td4" valign="middle" >


sha



</td>

<td class="td5" valign="middle" >


version or build number



</td>

<td class="td6" valign="middle" >


123abc



</td>
</tr>
</tbody>
</table>


**Getting started**




There are a few things you need to do to set this up for yourself. After cloning the code from [https://github.com/launchdarkly/legendre](https://github.com/launchdarkly/legendre), copy the [`custom_example.py`](https://github.com/launchdarkly/legendre/blob/master/custom_example.py) to `custom.py`, and fill it in for your environment.






 	
  * Set [`notify_sns_topic_name`](https://github.com/launchdarkly/legendre/blob/master/custom_example.py#L3) to the SNS topic that you want to use. It's okay if it doesn't exist yet; the script can create it, but you will still need to set the subscriptions to do something useful.

 	
  * Set up the [`app_status_resources`](https://github.com/launchdarkly/legendre/blob/master/custom_example.py#L5) dict to define the applications and tiers in your system. The URLs are meant to be status check resources (via a load balancer) that can be used to get the running version.

 	
  * Define [`get_expected_sha`](file:///Users/pkaeding/Documents/get_expected_sha) to determine what is the 'current' version of the given application in a given tier. Any different version will be deemed a zombie.




Also, the deploy needs a few environment variables set. Edit [`vars.sh`](https://github.com/launchdarkly/legendre/blob/master/vars.sh) to set the subnet and security group for the lambda function to run inside your VPC.




**Run the deploy script**




When you are ready to deploy, run [`./deploy_lambda_function.sh`](https://github.com/launchdarkly/legendre/blob/master/deploy_lambda_function.sh). This will:






 	
  * Package up the script with its dependencies into the zip format that AWS Lambda expects (as defined in [`pacakge.sh`](https://github.com/launchdarkly/legendre/blob/master/package.sh)).

 	
  * Interact with the AWS API to set up the lambda function with _most_ of the things it needs (as defined in [`scripts/setup_lambda.py`](https://github.com/launchdarkly/legendre/blob/master/scripts/setup_lambda.py)):

 	
    * Creates an IAM role for the lambda function to use. Review the json files in the [`scripts`](https://github.com/launchdarkly/legendre/tree/master/scripts) folder to see the permissions required.

 	
    * Uploads the zip file from the previous step to create a Lambda function (possibly publishing a new version if the function already exists).







However, there are a couple of things you still need to do:






 	
  * Add subscribers to the SNS topic. This will be highly personalized to your needs. Maybe you want an email sent. Maybe you want a webhook to notify your team in HipChat. Maybe you want it to trigger another lambda function that will kill the zombie instances. Maybe you want it to sound an air-raid siren. I'll leave this as an exercise to the reader.[
](https://blog.launchdarkly.com/wp-content/uploads/2016/04/2016-04-25-at-12.30-PM.png)[![example hip chat notification](https://blog.launchdarkly.com/wp-content/uploads/2016/04/2016-04-25-at-12.30-PM-1024x74.png)](https://blog.launchdarkly.com/wp-content/uploads/2016/04/2016-04-25-at-12.30-PM.png)


EDIT: Thanks to Twitter user [@chiradeep](https://twitter.com/chiradeep/status/725051658317774849) for the tip on how to set up Cloudwatch events to trigger a lambda task via the API.  I've updated the script to take care of this.
