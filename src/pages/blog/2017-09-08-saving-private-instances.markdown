---
author: joeryan
comments: false
date: 2017-09-08 17:00:10+00:00
layout: post
link: https://launchdarkly.com/blog/saving-private-instances/
slug: saving-private-instances
title: Saving Private Instances
wordpress_id: 2007
categories:
- Continuous Delivery
- DevOps
tags:
- compliance
- continuous delivery
- continuous integration
- on-prem
- on-premise
- private instance
- security
---

You are a new Director of Engineering at an enterprise company. The company has just moved your product to the cloud and is hosting in Microsoft Azure. You come from a tech startup where you ran all of your software in the cloud and focused on building product. So naturally you have just implemented instrumented monitoring with HoneyComb, Kubernetes to manage your containers, and you're thinking about leveraging serverless architecture.

You moved to this established enterprise company because they are providing technology to the healthcare industry and you are passionate about this space. They want you because you are good.

Now you face a challenge—how can I bring the good things from my _past_ role and pair them with the security standards and compliance in my new role? Well, let's first think about what the good things from your past role entails. Your previous team:



 	
  * Deployed 5 times a day

 	
  * Used feature branching

 	
  * Feature flag first development

 	
  * Implemented continuous integration


You realize you used 3rd party software for most of these good things, and had homegrown for others. You decide your first project is to research what software the new team is using, has built, and what software you will need to build and buy.


### Security and the cloud.


Now, before we dive in, let's consider the security standards and compliance you need to think about in your new role:





 	
  * Where is my data stored?

 	
  * What data is being sent over to the third party—is it PII?

 	
  * Where connections are made to third parties?

 	
  * How can I set different access control?

 	
  * How it will work when connection fails-redundancy?

 	
  * Is it HIPAA compliant?

 	
  * How is all this audited?




Like your new company, many companies are just starting to move key operations to the cloud. This is SCARY. Moving into Azure will allow your company to free up floor space, add more server redundancy, easily scale up and down, only pay for what you use, and focus resources on revenue generating activities— _security is still your responsibility._  And though these are all great things, you are not a security company.

![](https://static.notion-static.com/1c6fc56f36414a3e96130584ab46cdbd/giphy.gif)

Now you are tasked with bringing in these good processes, and they include 3rd party software providers. Products in this space are inherent in your development lifecycle and very close to your core application, but you need to ensure they are secure.

As we all know, most software providers in this space are cool tech companies in The Valley, far and isolated from the realities of your secure enterprise world. You look at on-premise options. And you remember that you’re driving change in the Healthcare space, not looking to manage infrastructure. The cloud options require a significant audit that is time consuming. A SaaS provider carries an ongoing risk that requires you store some data on 3rd party servers, which is a non-starter in Healthcare.


### **Is there a middle ground?**


There is one more option many software providers offer: Private SaaS, also known as a managed instance, Dedicated VPC, or private instance. You surmise if they do not have on-prem, private SaaS, or a really really good security team, then it's not likely their team is accustomed to working on enterprise challenges.

What exactly is a private SaaS offering? This refers to a dedicated single tenant, cloud software where the vendor manages the infrastructure.


### Why choose a private instance?


![](https://static.notion-static.com/f4b2d0ca3c2c4a11a8da994f14e6c4ce/giphy-2.gif)



 	
  * Single Tenant—You will have a dedicated set of infrastructure contained within a VPC. This eliminates the risk of noisy neighbors.

 	
  * Data Storage—Data can be stored in your AWS account or in an isolated section of the vendor's AWS account. This allows flexibility, if you are in the EU, vendor could spin up the instance in AWS in the EU.

 	
  * Residency—If you have a preference on where the instance is located or need to ensure proximity.

 	
  * Compliance—If you have additional security or compliance regulations, a private instance can be customized to fit your needs.

 	
  * Change Cadence—If you need to know when the software will be updated, you will have better insight and greater flexibility with a private instance.

 	
  * Integrations—If you have custom tools, integrations can be built.




### What's next?


You have narrowed down a few software providers for each job you are trying to solve (continuous integration, branching, feature flagging). You understand the value, the costs, and the security implications. You have chosen to stay in the cloud, which makes your infrastructure team happy. You have chosen to use private instances and SaaS where it makes sense, which makes your security team happy. And you have the tools you need to bring the good things into your new role, so you are happy.

Now you can focus on helping your company deliver product faster, eliminate risk in your release process, speed up your product feedback loop, and do it all securely.
