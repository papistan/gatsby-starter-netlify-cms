---
author: Kimh
comments: false
date: 2018-11-07 19:55:33+00:00
layout: post
link: https://launchdarkly.com/blog/how-atlassian-uses-feature-management-to-continuously-deliver/
slug: how-atlassian-uses-feature-management-to-continuously-deliver
title: How Atlassian Uses Feature Management to Continuously Deliver
wordpress_id: 193508
categories:
- Continuous Delivery
- DevOps
tags:
- Atlassian
- continuous delivery
- development cycle
- feature flag
- feature management
- Jira integration
---

_Originally published on [The New Stack](https://thenewstack.io/how-atlassian-uses-feature-management-to-continuously-deliver/), on Sept 28, 2018._

To remain competitive with other developer tools and collaboration platforms, Atlassian pushes teams to constantly improve existing functionality and release new features on a regular basis. So dev and ops teams are using feature management as a best practice to meet these goals.

Atlassian is a well-known software company that that aims to unleash the potential of every team. Best known for products such as Bitbucket, Confluence, Jira Software, Jira Service Desk, Hipchat, Statuspage and Trello — Atlassian currently serves more than 125,000 customers worldwide. Its products help teams organize, discuss, and complete shared work via project tracking, content creation and sharing, real-time communication, and service management.


### Feature Flagging


Atlassian measures team performance by the [OKR goal system](https://rework.withgoogle.com/guides/set-goals-with-okrs/), which focuses on key objectives and measurable results. This means team performance is measured with metrics like user satisfaction or mean time to resolution (MTTR hours). 

For increased efficiency, teams are organized cross-functionally into triads comprised of an engineering lead, design lead, and product manager so that projects have leadership and direction from these three vital perspectives. These three leads are responsible for strategizing and meeting the OKRs, and the combined groups are interested in building a technically correct features and making sure that value is actually delivered to customers. When a feature is rolled out its just as important that it delight customers and improve their experience, as it run smoothly without bugs. 

A recent example of this, is the successful launch of Jira Cloud. Bevan Blackie, a development manager for the Jira Cloud team, explained their approach: “How can we ensure that the things that we're doing are impactful for our customers?” Blackie said. “Ultimately, we don't want to get in the way of the work that they have to do, so that's a focus for us."

Before adopting LaunchDarkly, a few teams within Atlassian used an internally-built feature flagging system. It was primarily used to control feature releases, and with this system deployments were also tied to releases. This proved sufficient at first but, but as more teams wanted to use this in-house solution, some challenges arose: the system took time and resources to maintain. Different teams working with different languages needed help developing their own Software Development Kits (SDKs). And with no interface, this system was virtually unusable for nontechnical users. The result was that teams outside of engineering, including Product Management, relied on engineering support to turn features on/off or run beta tests, which became unruly when more teams wanted to use the solution. 


### Feature Management


Atlassian understood the value of feature flagging and what it could offer its teams, but with more than 2,000 employees at the time, the organization realized its home-grown solution wasn’t robust enough to meet its feature management needs. This is when they turned to LaunchDarkly. Blackie pointed out: “We couldn't deploy something and have it be switched off. Did we see a few incidents and some impact on customers in that kind of environment?” Blackie said. “Yes, we definitely did. I was cast with driving the uptake of LaunchDarkly internally, and it was about this concept of separating deployments from releases.”

The first team to adopt LaunchDarkly was able to get started pretty quickly. SDKs are standardized, well maintained, and available in all major languages, so developers can setup LaunchDarkly in their stack in a matter of minutes. In the months following, other teams started using LaunchDarkly. For the first time, teams had visibility into their feature flags from a central location. 

With LaunchDarkly, more and more teams across the organization now have the ability to separate code deployments from feature releases. When developers begin to build a feature, they simply wrap it in a flag, and then control it from the LaunchDarkly dashboard. This means teams can ship code at anytime with flags turned off and features hidden, and then turn the features on when they’re ready. “My teams can focus on things that are really going to add value to our customers, rather than worrying about other things that are coupled but not directly related to a specific feature,” Blackie said. “This translates to teams spending more time focusing on the items that differentiate us as a company.” 

Teams also have better control over segmenting their user base. Instead of switching something on/off for everyone, they now build cohorts and expose different groups to different features in a highly targeted fashion. Teams are now testing, getting feedback, and iterating while working through projects without having the changes dependent upon each other. 

But developers are not the only LaunchDarkly users at Atlassian. The easy-to-use interface made it possible for other members of the triad or product management team to create their own specific cohorts, independently run beta tests, gather valuable feedback on new features and product usage. Once engineering puts a flag in place, anyone can easily control the flags from the LaunchDarkly dashboard. Non-technical team members started to become more involved in the feedback loop and development cycles. "It's a collaborative exercise for us. In the past, feature flagging was seen as a technical exercise and it didn't really involve everyone in the team,” Blackie said. “But now because we're talking about different types of customers and targeting all the attributes that our customers have, it’s much more of a collaborative exercise." 


### Continuous Delivery


Within a year, one team saw NPS scores increase—with customer feedback specific to performance and usability—and MTTR hours improve by 97 percent. These improvements have been driven by a cultural shift to a continuous delivery approach. While LaunchDarkly is not the only continuous delivery tool in use, they recognize that feature flagging and feature management are an integral part of making the continuous delivery process successful. 

Blackie also pointed out that "LaunchDarkly is a very integral part of our release cycle today.” 

“Many of our developers use it, and most features we’re building are wrapped in feature flags,” Blackie said. “The features are switched ‘off’ by default and when a developer is ready to turn it on they have a nice dashboard to watch the change roll out." 

One team used LaunchDarkly to [rolled out new Atlassian UI Design (ADG3](https://blog.launchdarkly.com/the-customers-wont-be-happy-how-atlassian-rolled-out-a-large-scale-ui-change-for-confluence-cloud/)) to Confluence Cloud. Because they were changing the UI so much, the team thought through how customers might be impacted and were careful in how they delivered theat new functionality to users. Having control over the new features allowed them to beta test and validate the new functionality, and then slowly roll out the features to the entire user base. Furthermore, slowly rolling out new functionality meant their own support team could handle a spikes in requests. 

“It's simple,” Blackie said, “we're able to ship value to some customers faster and get feedback sooner, which improves the overall experience.” 

The Jira Software team has recognized that LaunchDarkly has been critical to their success — specifically having the ability to target specific users, test features early and often, and get valuable feedback. Without a continuous delivery approach, this recent project could have been a multiyear project. But, in just a matter of months, the team has been able to ship value to customers and gather feedback for future releases.  


### The Full Development Cycle


Recently, Atlassian and LaunchDarkly debuted an [integration with Jira Software](https://www.atlassian.com/blog/jira-software/feature-flagging-integrations), Atlassian’s widely used issue tracking system. While developers and product managers have found value in using LaunchDarkly’s feature management platform to safely deliver and get feedback when working on new features, operations teams can now utilize this integration to work faster and reduce context switching. 

From Jira, teams can see and control their feature flags. The visibility this integration provides includes not just seeing which feature flags are in place, but also if it has been turned on and what user segments are currently experiencing the feature.  

This recent integration has made it clear how important feature management is for teams across Atlassian. With more control over the features they’re building and shipping, they can move faster and deliver value with more confidence.
