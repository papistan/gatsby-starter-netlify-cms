---
author: andreaech
comments: false
date: 2016-11-29 18:15:01+00:00
layout: post
link: https://launchdarkly.com/blog/toggle-talk-with-damian-brady/
slug: toggle-talk-with-damian-brady
title: Toggle Talk with Damian Brady
wordpress_id: 1196
categories:
- Continuous Delivery
- DevOps
tags:
- configuration switch
- continuous delivery
- Damian Brady
- dev tools
- DevOps
- feature flag
- feature flaggins
- feature flags
- feature toggle
- feature toggles
- NDC Sydney
- Octopus Deploy
---

I sat down with [Damian Brady](https://twitter.com/damovisa?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), Solution Architect at [Octopus Deploy](https://octopus.com/) for a conversation about his experience with [feature toggles](https://launchdarkly.com/use-cases/?utm_source=launchdarkly_blog&utm_medium=organic).  He shared with me his tips for best practices, philosophies on when to flag and what he thinks the future of feature flagging will look like. 



 	
  * **How long have you been feature flagging?**


I had to think about this one a bit - about 8 years ago but I probably didn’t know what it was called at the time. 


<blockquote>_"It’s definitely the case that people are doing this without knowing the name “feature flag” or even giving it a name. They’re just saying it’s a configuration switch or a toggle and but not giving it a more proper name, they’re not identifying it as a first-class citizen really." _  </blockquote>





 	
  * **What do you prefer to call it and why?**


Now I call it feature flagging or occasionally feature toggles. I think toggles makes a bit more sense as analogy for non-technical people.  



 	
  * **When do you think feature flagging is most useful?**


There’s a couple - but the one I think it’s most useful for is to use a feature flag when you have a feature that is nearly complete or complete from your point of view. Either way, you are ready to get verification from someone with real data.


<blockquote>_"You can test as much as you want with your pretend fake data, or even a dump from production which is being obfuscated, but until it gets used in the wild you’re never really sure that the feature is doing exactly what it needs to do."  _</blockquote>


So hiding that behind a feature flag, and then clicking it on for somebody who is using the product for real in any way gives you that last little test that is ultimately the most useful.  At that point you still have the opportunity to back out. If something was corrupt or your expectations were wrong, it’s really useful for that last-minute check.  

At Octopus, we’ve started using feature flags for big features that a lot of people don’t want to see. So a while ago we introduced the idea of a [multi-tenant deployment](https://octopus.com/docs/guides/multi-tenant-deployments). And probably most of our users don’t need that feature because it adds a lot of complexity to the UI.  We have a configuration section where you can toggle an “on” and “off” switch, so if you don’t need that feature you can just leave it off.     

**Are there any cases where feature flagging is not a good idea?**

I think there are two extremes where feature flagging is not a good idea. On one hand, flagging really small changes can be more trouble than it’s worth. It’s introducing an extra level of complexity that maybe for a small change is not critical.  

On the other side, using feature toggles around the architectural changes in the core of your application - that’s kind of hard to test. Do you have a feature flag that when you turn it “on” it completely redirects the way the entire application will run? In that case you bite the bullet and decide that this is a big change and you’re just going to have to [test it very thoroughly](https://featureflags.io/canary-testing/) and not give yourself a way out.

That being said, there are some cases where you still need to give yourself a way out by using a flag. For example, you might deploy some new feature thinking it's correct, but subsequently learn from a customer or user that it doesn't really meet their needs. Rather than the user living with a bad feature, you might want to turn the flag off and go back to the drawing board.

If it's an architectural change, you may only find out that there's a bug when you use it in production. Test data may not surface the issue properly.

Ultimately, doing core architecture changes in a way where you can back out later can be an extra huge amount of work. It’s probably at that point you know you aren’t going to do it (revert back) anyway.   



 	
  * **Best use of a feature flag - a personal story? **


When I first started using feature flags, around the 8 years ago timeframe, I was working on a web application that was internal and a big line of business.  And we had just added a new third party provider for providing SMS.  And with this new provider, it meant we had to write a lot of new code.  It was internet banking software so it was a one-time password we were sending out - and it was really really important that it work.

We tested everything rigorously but wanted more insurance.  So we put the new service behind a feature flag. We had a bunch of agents that ran this type of SMS. We enabled a flag for one of the agents and monitored it to make sure it was actually doing the right thing and not failing. And then we started trying other ones. It failed a couple of times because of differences in the sandbox environment between the third-party provider and the real one.


<blockquote>_"We thought everything was okay, but when we put it live we turned it on slowly, and it didn’t do what we expected."_</blockquote>


So when that happened we turned it back off again...and went back to the drawing board. 

So without the feature flag, we would have dropped every person using the service at that critical point. That client would have not been able to receive SMS’s until we were able to rollback. 



 	
  * **What do you think is the number one mistake that’s made around feature flagging?**


There is one that I keep seeing - when you wrap a new feature you believe to be finished in a flag, the biggest mistake with this is not testing that change with the flag “on” and then “off”. For instance, when you turn it “on” it snaps into new database tables or starts changing the way data is saved. But when you turn it “off” again, you’ve lost that data or data is corrupt. For this you need to test it “on” and “off”.  


<blockquote>_"If you have more than one feature flag running at the same time, test the combinations of them being both 'on' and 'off'._"</blockquote>


If they’re likely to interact with each other you need to test “one on, one off,” “both on,” “both off” and all possible combinations like this.  



 	
  * **How do you think feature flags play into the DevOps movement? What about Continuous Delivery?**


I think feature flags play in both continuous delivery and continuous deployment. I think they’re most useful to continuous deployment. You have all of your features pushed out to production as soon as they compile essentially - but they are behind a feature flag so you don’t break anything. That’s the way Facebook does it. They know that any new code they write might end up in production so it’s going to be safe behind a feature flag.  


<blockquote>_"The design of the DevOps movement, the aim of it really, is to get real features and real value in the hands of users as quickly as possible."_</blockquote>


So if you have to wait until this “half done piece of work” is actually safe to deploy then that slows you down. So having it behind a feature flag so that it doesn’t get touched until you are ready to test it can be really powerful for increasing velocity and getting things out to production much faster.     

So even for marketing teams, it means they don’t have to tell the developers “hey we worked out the result of this a/b test and we want option b.” If the marketing department can just just flip that switch and say “no, option b is working better so just leave it there” without a new deployment or contacting the developers to remove the old stuff and redirect to the new stuff,  that increases that team effort of getting value to customers which is the whole purpose of DevOps. 



 	
  * **Can you share any tips for better flagging?**


If you’re feature flagging a big change, pair the feature flag with a branch by abstraction pattern. [See the clip from my talk from NDC Sydney for more details.](https://vimeo.com/171950824#t=30m)

There’s also the concept of transitional deployments - again [refer to my video clip here for more](https://vimeo.com/171950824#t=28m16s). It’s useful for things like database schema changes where you have a midpoint for both the new and old applications that will work with the schema that’s currently there. So you can turn that feature off if you need to. 



 	
  * **Are you seeing feature flagging evolving? If so how?  And how do you expect it to change in the future?**


It’s been around for a long time...but I think it’s becoming much more visible - and partly it’s LaunchDarkly helping with that. I think more people will start using feature flags in their continuous delivery pipeline. And the more continuous delivery becomes mainstream, the more mainstream developers will need feature flags.  


<blockquote>_"I think feature flagging is starting to be something that you have to add your deployment cycle because you know it needs to be fast and you know you feature needs to get to production as quickly as possible - and feature flags are the way to do that."  _</blockquote>


So as it becomes more mainstream I think there will be more tools, more frameworks, more awareness of it (feature flags) as it hits more and more companies. I think there will be things coming out like feature flag-aware testing tools - so testing tools that know that they need to test with this flag on and off.  

The summary - more tools around best practices around this thing which is becoming more mainstream.  With DevOps becoming more popular, more people are thinking “yes we need to get to production quicker, we need that cycle time to reduce” so it’s a natural extension I think to start solving some of those problems with feature flags.  


<blockquote>_"I think it’s just starting to become more mainstream frankly because it’s a solution to a problem that is starting to become more mainstream."   _</blockquote>
