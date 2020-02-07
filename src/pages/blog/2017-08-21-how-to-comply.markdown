---
author: az
comments: false
date: 2017-08-21 17:50:32+00:00
layout: post
link: https://launchdarkly.com/blog/how-to-comply/
slug: how-to-comply
title: How to Comply
wordpress_id: 1904
categories:
- Product Updates
tags:
- A-Lign
- compliance
- security
- SOC 2
- SOC certification
---

_Everyone loves a little affirmation (Image credit: _[_twitter_](https://twitter.com/nccgroupinfosec/status/400904784871309313)_)_


_Things we wish we had known and things we were happy that we implemented early. _

At LaunchDarkly we recently embarked on the journey to SOC Type 2 compliance. While the reasons we chose to pursue this certification were primarily business driven, the tasks and actions incorporated into the process most directly impacted our engineering operations and development teams. And due to the experience and philosophy of the founding engineering team, the actually impact of the process was minimal. 

Once deciding to sally forth on SOC certification (or any security and compliance certification for that matter) you will be in a much better position if you view the criteria of the certification as a benefit (or imperative) of good business practices. If you are in search of the certification primarily as a way to sell into certain customers or verticals, you will likely be frustrated with this entire process. Security is like diversity—you need to inherently believe in the value to be successful in implementations and outcome. 


<blockquote>“So, what are these criteria you speak of?”</blockquote>




#### **Need vs. want**


The[ principle of least privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege) is a well-known concept where you only provide access to the people that actually _need_ it. This also extends to the level of access that is given. Ultimately this distills to: _view_ vs _control._ I like to start here because this is a forcing function for so many of the other criteria. When you are thinking about who should have access to each system/service, you are inclined to:



 	
  * Define roles

 	
  * Log activity based on user/account

 	
  * Build review process for accounts


On-boarding each new employee gives you an opportunity to review the tools you use to run your business, question who needs access, and to what extent. 

This is also a great time to introduce new employees to another key security maxim: _Trust, but verify_. This concept is relevant in the context of the access that accounts or component services assert are needed, as well as the way that you validate user accounts. 

For services—either 3rd party or just components of a larger service—you should know what information is being stored, and where. Ideally, you are being thoughtful of the first principle of least privilege. 

This is especially true of customer data. The easiest way to protect data is to limit what you collect. Second is to make sure that you are being intentional and explicit with where you store the data. Finally, you need to look at the access policy that you put around that data.

For user accounts, multi-factor authentication (MFA) or two factor authentication (2FA) significantly increases your ability to validate that accounts are only being accessed by account owners. 

Another time to plan for is employee off-boarding—ideally, before you off-board your first employee. This is also a good time to review your tools and access privileges. 


#### **Context; not blame**


When a single developer is working on building a service, logs are primarily useful for understanding how well things are working (or where they broke). As the number of individuals working on the system becomes larger, the ability to know who changes what becomes increasingly important. 

One caveat is that as you incorporate the ability to know _who,_ you leverage this data to build context around _why_ things changed, rather than simply using it as a means to place blame. If one person can bring down your service, then you probably should direct blame at the architect of the system. (Unless that destructive individual and the architect are the same person ¯\_(ツ)_/¯). 


<blockquote>“A log without account context is like a novel without characters.”</blockquote>


A log without account context is like a novel without characters. You can build a picture of what happened, but likely will miss _why_ things happened. If you don’t know why, you’re unlikely to prevent it from happening again. 


#### **Built for toddlers… or failure**


[![](https://blog.launchdarkly.com/wp-content/uploads/2017/08/giphy.gif)](https://blog.launchdarkly.com/wp-content/uploads/2017/08/giphy.gif)


_Failure is trivial compared to proactive destruction (image credit: [Lego City](https://giphy.com/gifs/lego-lego-city-l3q2SiQ4Brr4vzCV2/))_


The stability of a service is often a strong indicator of the inherent security. After all, the most common exploitations are based on overloading some resource. Thinking further about the elimination of blame from building a secure and stable service, failures should be viewed as opportunities for increased robustness. This is where building for toddlers comes in.

Toddlers are the ultimate destroyers. It is the developmental stage where everyone starts to experimentally test the laws of physics. Gravity, entropy, projectile motion, harmonic oscillation—they’re all put through a battery of tests. 

Ideally, you are thinking about your service from the perspective of a parent (or guardian) that is toddler-proofing their home. Bolt things down, put breakable things out of reach, lock up the flamethrower, and embrace the fact that you will miss things. For the items you miss, have an emergency procedure in place and appropriate medical supplies on hand. 

Back in the context of your service…


#### **Write it down… or it never happened**


Your code/feature is not ‘done’ until the docs are written or updated. Services require constant supervision and are never ‘done’. But if a developer builds or changes something and doesn’t write it down, then they effectively become the only individual that is able to monitor or operate the entire service (at least with all the context).

So, what should you write down? “Everything,” is the easy answer, but often not the complete one. You want to write down enough to provide context if any component starts doing something unexpected. 

If you don’t know where to start, a good approach is to write down what would need to happen if your service was deleted. How would you rebuild and restart your service? How would you restore your data? 

Next you can look at the impact/process of the loss of each individual component service. The important part of this is to incorporate the documentation into the development process to ensure that as your service evolves your documentation is always up to date—otherwise, the change doesn’t exist after a failure. 

Great, now you know what to do next time AWS S3 needs to reboot. But, what about your customers? The next step is to write down an action plan for service interruption. Make sure you have a process and plan in place for keeping folks in the loop. 


#### **Security is not the french fries**


If you are in a situation where you are looking to “add” security, you are likely going to be in good company with Sisyphus. Security needs to be a part of your foundation—it is not an “add-on”. But if you are realizing this is now—that security is a requirement for your business— you can do more than wish you had considered it sooner. It is not too late, but it is not a quick fix that you can solve with a certification. 

First you need to implement the security in your foundation and process. Make sure that it is part of your culture. Once you have a culture of security and process, compliance is just providing proof of your culture.


#### **Now… about that certificate**


You don’t show up to your official Genius Book of World Records judging day having never practiced juggling 9 clubs. Same goes for when you decide to get your certification for SOC. 

However, when you build a strong foundation and culture for security and compliance, then the steps to get certification are rather straightforward. You call up your friendly neighborhood SOC auditor and get a copy of their check list. 

In the case of LaunchDarkly we worked with the fine folks at[ A-lign](http://www.a-lign.com/). After an initial conversation we retained their services to conduct an independent audit of our systems and practices. 

A few months prior to the audit, A-Lign provided our team with a checklist of all the documentation and proof they would need to see when they came onsite for our assessment. This afforded us the opportunity to ensure that all of our practices were organized and in a state that could be easily evaluated. 

When the time came for the audit the auditor spent three days* on-site interviewing members of the team and reviewing our practices. After the on-site visit, we were informed that we had passed the initial competence certification. 

Of course, now that we have gone through the validation process for one certification, it seems like a good time to keep going for a few more. Many of the certifications have a significant overlap in requirements. They are all looking to establish trust and ensure the service provider is operating in the best interest of the customer. And it turns out, most customers define trust in a very similar way. 
