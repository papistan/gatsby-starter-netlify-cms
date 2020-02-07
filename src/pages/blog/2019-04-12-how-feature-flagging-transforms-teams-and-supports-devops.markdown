---
author: Kimh
comments: false
date: 2019-04-12 21:28:48+00:00
layout: post
link: https://launchdarkly.com/blog/how-feature-flagging-transforms-teams-and-supports-devops/
slug: how-feature-flagging-transforms-teams-and-supports-devops
title: How Feature Flagging Transforms Teams and Supports DevOps
wordpress_id: 193843
categories:
- DevOps
- Feature Management
tags:
- Atlassian
- BrandVerge
- collaboration
- feature management
- webinar
---

_Originally published on [The New Stack](https://thenewstack.io/how-feature-flagging-transforms-teams-and-supports-devops/) on 27 February 2019._

Move fast, don’t break things. Delight the customer. Meet SLAs that limit downtime to absolute minimums. Keeping pace with the customer expectations and the competition today is a tall order. Releasing more, faster is risky, and can transfer undue burden from development to operations and even business teams within an organization. In response to these pressures, many software development teams have adopted new methodologies and tools to help them accomplish this gracefully. 

One approach that has proven successful is promoting cross-functional communication. Atlassian, in particular, has formalized this practice by creating [triads](https://www.atlassian.com/company/events/summit-us/watch-sessions/2017/team-culture/triad-magic-how-product-design-and-engineering-work-better-together)—development teams comprised of an engineering lead, design lead, and product manager. With leadership from these three areas, projects are sure to benefit from direction from these three vital perspectives. All three leads are responsible for strategizing and ensuring goals are met. And their combined groups collaborate throughout the development cycle to build technically correct features that deliver value to customers. Atlassian has found that by bringing together leadership like this and holding them equally accountable, the resulting work will do more than just run smoothly, but also delight customers and improve their experience.

There are many other organizations that have found value in promoting cross-functional collaboration. Like Atlassian, most agree this is a great way to help teams move faster without compromising value to the customer. But many who have taken this approach would also agree this cultural shift benefits strongly from tools that help maintain good communication and visibility. Jira, Slack, GitHub, Bitbucket, and Confluence are all tools we’ve heard of, even if we haven’t had a chance to use them yet.


### Getting a Running Start


Of all these tools, feature management stands out to us. (Surprise?) We know many teams feature flag, but we’ve noticed _how_ teams are transformed when they incorporate centralized feature management systems into their processes. When teams are [feature flagging](http://featureflags.io/feature-flag-introduction/) they’re already thinking about managing their release processes. So of course, when they begin to centralize visibility and functionality around feature flagging, the benefits extend beyond engineering.

We recently sat down with product managers from Atlassian and BrandVerge to talk about the [impact feature flagging has had](https://launchdarkly.com/webinars/better-team-coordination/) on on supporting this kind of collaboration and how it has changed development cycles within their organizations. [Taylor Pechacek](https://twitter.com/tpechacek), Senior Product Manager at Atlassian, and [Marc Devens](https://www.linkedin.com/in/marcdevens), Director of Product at BrandVerge, shared their experiences with LaunchDarkly’s VP of Product and Platform, Adam Zimman.

Taylor and Marc both pointed out that when feature flagging is a part of the strategy for developing new features, before work begins they’re already thinking about where to put the flags and how to instrument them. This means their teams need to understand what they’re building, who should see it, and what the success criteria are. Is it a VIP feature intended for a small subset of users? Will it be a core feature that at some point all users should have access to? Or is this an opportunity to test and validate new ideas?

At the highest level, considering these elements before building is beneficial enough. Coming to agreement on project specifications helps everyone involved understand and agree upon what is being built and what the expectations are. But even more than that—when engineering, product, and design can agree on those important aspects, then development cycles move faster and run more efficiently. 

Mark Evans also pointed out that beyond being on the same page, the very nature of having feature flags in place affords his team flexibility in the long run. “One of the things that we really benefit from is the ability to change things up at a later point,” he said. Getting started with everyone on the same page and a clear sense of direction is great, but it’s also valuable for Evans’ team to have the ability to quickly pivot if they need to. When they get feedback and need to iterate, they can keep moving forward quickly.


### Now You See It


On a deeper level, these teams have have found visibility and communication has improved throughout their development cycles. Yes, starting with everyone on the same page is great, but once work begins, these teams now have a central platform where everyone can get visibility into the new features being built. They can stay on the same page.


<blockquote>“That has really shifted all of the way that I think about planning…You actually get into this mode where it's much more about that whole ‘build, measure, learn' mantra and these feedback loops. How you manage those feedback loops, how you're responding to customers, how you're iterating, how you're evolving.” - Taylor Pechacek, Senior Product Manager at Atlassian</blockquote>


Before using a feature management platform like LaunchDarkly, only the development teams would have knowledge of what was in the code base. In some larger organizations, different dev teams might not even have a good method of sharing this knowledge between them, information is siloed. A feature management system brings visibility around features wrapped in flags to other teams. They can see what exists, who owns it, how it has been instrumented, and they now have the means to actively participate in testing or releasing. 

Improved visibility means if you’re a part of the extensive team of people helping to build, release, and promote the usage of a feature, you have a better sense of what its status is and how your role might be evolving. Even if you’re not directly involved in building or marketing the feature, you can still get a sense of what it is. Teams across the organization, from marketing and sales, to customer success will benefit. Other dev teams building other features can better understand how their own projects might be affected by dependencies and plan appropriately.


<blockquote>“As a product manager I'm making sure that everyone that needs to be aware of an upcoming feature knows all the details about it, that we have support documentation already, that everything that's necessary for that release is done before anyone's even seen it.” - Marc Devens, Director of Product at BrandVerge</blockquote>


Both Taylor and Marc pointed out that when visibility improves, team members across cross functional groups will have a stronger sense of ownership and clearer paths of delegation. Even if you are feature flagging, with no central system to manage your flags, its difficult to understand what exists and what status the features and flags are in. When teams have shared visibility and have a stronger sense of who is doing what, ownership over features and their associated flags becomes possible. You can assign individuals or groups to actual features, flags, or moments within the development process. 

“The key thing for us though around ownership is all about visibility. So, we need to know who owns that feature flag, or at least who knows about it, and how that actually interacts with other feature flags,” Pechacek said.

Taking this a step further, a centralized view allows for delegation. With visibility, ownership, and a platform that allows anyone to control features once placed in the codebase, teams can share the tasks associated with testing, releasing, and managing features. Now dev can focus on building, and give control over releases to product, marketing, or any other team. This removes pressure from engineering teams, and allows other teams to more actively participate in the release process—whether for experimentation and feedback loops, or rolling out products to users. 

“A customer success team member could be on the phone with a customer that is asking about that, and they can just drop it right in the person's account while they're on the phone with them,” Devens said.

With feature management, teams have stronger ownership over what they’re building, from concept, to launch and control, and finally to cleanup when the release is complete and it’s time to remove flags. To hear more of the conversation around how feature management empowers cross functional collaboration, check out the [recorded webinar](https://launchdarkly.com/webinars/better-team-coordination/). Taylor Pechacek, Senior Product Manager at Atlassian, and Marc Devens, Director of Product at BrandVerge talk with Adam Zimman, VP Product & Platform at LaunchDarkly about how they’ve been able to improve visibility and communication around product releases. 
