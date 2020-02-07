---
author: edithharbaugh
comments: false
date: 2015-03-18 19:44:16+00:00
layout: post
link: https://launchdarkly.com/blog/how-workhands-moves-quicker-building-better-applications-with-launchdarkly/
slug: how-workhands-moves-quicker-building-better-applications-with-launchdarkly
title: How WorkHands moves quicker building better applications with LaunchDarkly
wordpress_id: 64
categories:
- Continuous Delivery
- DevOps
---

LaunchDarkly’s new features helped a company find the best solution to manage two websites, optimize registration flow and user management for more than 25,000 users.


## About WorkHands


WorkHands is a platform that connects the blue collar workforce. Skilled trades specialists (such as welding, machinery and manufacturing) use WorkHands' online platform to connect with workers, employers, unions, apprenticeships and organizations. Skilled workers can build and manage their professional identities online by showcasing photos of their work, uploading certifications and filling out a profile with their work history and education. Patrick Cushing, WorkHands' CEO, believes that WorkHands is "an 'identity service'... providing a place for you to own your own identity." Employers, organizations, unions and apprenticeships use WorkHands to find skilled workers, post new announcements and job opportunities. Since their launch in September 2014, WorkHands has more than 25,000 users across 50 states.


## Not Fitted Enough


Patrick Cushing described the first version of WorkHands as "a Linkedin clone". They noticed specific features and functionalities affecting user engagement and the ones that were most utilized were hacks to the original system. After analyzing engagement patterns they reached out to their existing users to understand their requirements. WorkHands decided to build a tailored product. This resulted in a separate website built entirely from scratch incorporating their best practices making it, as Patrick Cushing illustrates, "much better, cleaner and easier to use". With six employees, WorkHands knew they had to either hire more staff or find a solution to manage two sites, registration flow and user management.


## Fit to Perfection


During the build of WorkHands' second website, Patrick Cushing was introduced to LaunchDarkly - a continuous delivery platform. LaunchDarkly enables software teams to launch, test and optimize features. For Product Managers, it allows for quick feature iterations. For Developers, there's native SDK support for almost every development platform including Python, Ruby, Go, Java, C#, JavaScript and PHP.


## Management


Managing multiple sites can be cumbersome. With the addition of the second website, WorkHands was excited to have LaunchDarkly implemented so that they didn't have to worry about which user went to which site and the constant task of switching between two sites. As part of their on-boarding process for new schools and organizations, WorkHands was in control of who they allowed into the sites. Patrick Cushing mentioned the toggle sliders in LaunchDarkly gave their sales team the flexibility to demonstrate the software at any time. LaunchDarkly gave them complete control. Before they had to deploy a brand new version of software every time. Using LaunchDarkly, they were able to quickly turn on and off features without having to deploy. Patrick reminisced about his old job where he "was having to manage multiple sites and having to build the infrastructure around who saw what." With LaunchDarkly, "It's just so nice we don't have to do that."


[![workhands-20150317100337](https://blog.launchdarkly.com//wp-content/uploads/2015/09/workhands-20150317100337.png)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/workhands-20150317100337.png)





## Let's Redirect


Patrick Cushing emphasized WorkHands' focus on being a simple design that didn't require a full day training for the platform for their members. This is a competitive advantage as other websites have a non-intuitive interface making it difficult for users to navigate. Getting started with WorkHands is "Easy for them to set up. They claim the network and begin the process. Everybody who is associated to them gets redirected to that new site using LaunchDarkly." From the user's point of view, the experience is seamless. From the administrator's point of view, the user is flagged so that when they sign in, they are identified as being part of the pilot program and automatically switched to the new site. If by chance the user lands on the old site, they are able to navigate to the new site with LaunchDarkly configured to display a back arrow in the navigation bar. "One of the things that's really neat that they've just added is that we can actually go in per person to turn these things on and off where it used to be a blanket function. LaunchDarkly is incredibly easy to use” touts Patrick Cushing.


[![redirect](https://blog.launchdarkly.com//wp-content/uploads/2015/09/redirect.png)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/redirect.png)





## Rollout Percentage Feature


LaunchDarkly allowed WorkHands to focus on building their product and not their infrastructure. With more than 25,000 people using their old site, WorkHands was concerned about how they would slowly let the users into the new site. They wanted to test 5% of the users before opening it up to their entire database. They found the Rollout feature in LaunchDarkly to be the solution. Patrick Cushing points out, "We're really excited about being able to use LaunchDarkly to slowly, percentage wise, increase who actually comes onboard. We are going to be able to manage this in a way that, usually if we were a large organization, you would have to have a lot more infrastructure."


[![rollout](https://blog.launchdarkly.com//wp-content/uploads/2015/09/rollout.png)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/rollout.png)





## About LaunchDarkly


LaunchDarkly is the “last mile” in continuous delivery, separating code deployment from feature rollout, and pulling business logic out of code and into an easy-to-use dashboard. This separation allows customers to ship code faster, optimize their features, and iterate more quickly. LaunchDarkly gives smaller companies pinpoint control over features in ways that were previously only possible with massive infrastructure investments at large companies like NetFlix, Etsy, Facebook or LinkedIn. By powering responsive products, LaunchDarkly customers can launch at small percentages (1%) as a quick smoke test, as well test out features on small segments of users to experiment on what functionality performs the best. But LaunchDarkly is more than an A/B testing tool— companies can use LaunchDarkly to personalize user experiences across their entire platform, from web to mobile and even desktop. For example, a SaaS company can control their freemium vs premium features or a new user experience that’s different than a power user experience. Companies can even use LaunchDarkly to cleanly sunset features that are underutilized or unpopular.



* * *





###### _LaunchDarkly helps you build better software faster with feature flags as a service. Start your free trial [now](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
