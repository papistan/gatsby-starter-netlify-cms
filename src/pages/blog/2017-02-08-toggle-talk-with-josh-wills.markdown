---
author: andreaech
comments: false
date: 2017-02-08 17:53:41+00:00
layout: post
link: https://launchdarkly.com/blog/toggle-talk-with-josh-wills/
slug: toggle-talk-with-josh-wills
title: Toggle Talk with Slack's Director of Engineering Josh Wills
wordpress_id: 1366
categories:
- DevOps
tags:
- data science
- DevOps
- experiments framework
- Facebook
- feature flag framework
- feature flagging
- gatekeeper
- Google
- machine learning
- Slack
---

I sat down with [Josh Wills](https://twitter.com/josh_wills?lang=en), Director of Engineering at [Slack](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwjHxsT5_u3VAhUM7yYKHcczClYQFggzMAA&url=https%3A%2F%2Fslack.com%2F&usg=AFQjCNELhY6evRw6gqROHJjRiMRXHK-dXA) and unabashed feature flag enthusiast, to get his opinions on the practice, where it’s most useful, and how it has played an important part in his career.  I think my favorite take-away from him was, 


<blockquote>_"Feature flagging is scary. I get why it's scary. But to me, not launching your product every five minutes is scary... Launching continuously is how you learn fast-- It's not just about deploying fast, it's about learning fast. That's the future of viability."_</blockquote>


Here’s what I heard from Josh in the interview.  
****



**How long have you been feature flagging?**

I started feature flagging at Google in 2007, and when I joined the team they were in the middle of rewriting the feature flag system. Our feature flag framework was called the Experiments Framework because it was designed for running A/B tests, and it grew out of that into this very powerful and complicated feature flagging framework that we used for literally everything. It started out as a simple “feature on”/“feature off” system, but it evolved to include richer types like strings and floats and even had some simple conditional logic for modifying flags based on attributes of the request. It became the system through which all of Google's various machine learning models were combined to make decisions for ad ranking, search ranking, etc. 

Imagine that you have dozens of [machine learning](https://www.forbes.com/sites/bernardmarr/2017/05/04/what-is-machine-learning-a-complete-beginners-guide-in-2017/) models active on a given request, doing all kinds of different things, and your job is to figure out an algorithm for deciding which ads should go where and how much each advertiser needs to pay. All of those different signals are combined together through a complicated series of equations which have a bunch of thresholds and weights. There's very rich logic in not only the machine learning models, obviously, but also within the feature flag framework, to control under different contexts what counts the most.


<blockquote>_Trying to do data science and machine learning in production without feature flags is nuts._</blockquote>


The feature flag framework here at Slack was developed in-house and was not initially developed with data science in mind, but we eventually created one that was to support our own search ranking, backend performance, and new team onboarding experiments.


<blockquote>_ But when I got here, I was so happy that they had a feature flag framework at all-- it means you deploy code hundreds of times a day, not once a month, or whatever it is other companies do._</blockquote>




**What do you prefer to call it and why?**

I like to call it the experiment framework, but that's just Google/Xoogler nomenclature. [Facebook's system is called Gatekeeper](https://www.facebook.com/notes/facebook-engineering/building-and-testing-at-facebook/10151004157328920/) and it's basically the same idea. Most of these systems have converged to have the same set of features, because it just makes sense and you have to have certain things. Eventually you'll get there anyway, so why not just skip to the end?  
****



**When do you think feature flagging is most useful?**

I'm biased, since I'm a data person. Data science, machine learning is what I do and I think it is absolutely critical for machine learning, for bringing any kind of data driven feedback loops and intelligence into your application. That is when it is absolutely most critical. 


<blockquote>_You should not be doing machine learning without a feature flag framework. _</blockquote>


If you are saying, “Oh I want to get into machine learning, and I'm going to do predictions or personalization or recommendations,” which lots of people do, and you are doing it without a feature flag framework, you are insane and should be fired. Not to put too fine a point on it, but...



**Are there any cases where feature flagging is not a good idea?**

Well, there is always tech debt that goes along with doing this kind of stuff. We deal with this at Slack, and Google deals with it as well. You end up with code that has a lot of “if” statements in it. Engineers are not always the best about deleting their feature flags once they're no longer necessary.

So we have a whole archival system, so that when you do the code review to create the feature flag, you also have to specify when you plan to delete the flag, and get alerts if the flag is not removed by such-and-such a date. That is the cost of doing business. I would say the benefits massively outweigh the costs.

I think there are certain other situations where feature flags are not a good idea.  They’re relatively rare, but they do happen. Where you're switching backend systems there can be times where you have to just go for it. You maybe reach a point where you just can't quite bring yourself to burn the bridge and just go without the old system anymore, even though it's causing you pain, and you know it needs to go. You just need to bite the bullet and do it, do the cut over and live with the consequences.


<blockquote>_You work super hard to not ever find yourself in that situation. No team is going to go out of their way to corner themselves like that, but if you're cornered, you've got to fight your way out._</blockquote>




**Best use of a feature flag - a personal story?**

It's been crucial to the way I’ve worked ever since I moved to San Francisco. Coming from the perspective of doing machine learning, data science, etc. at Google, I ran thousands of experiments all in search of new ways of combining different models together, in order to fundamentally make Google more money, make the user experience better, and generate more ROI for advertisers. I got really good at it. You could say that feature flags made my career.

At the same time, there was one Friday afternoon back in 2009 where I thought it would be a good idea to do one last push, and I launched a bad feature flag configuration that broke the ads systems and cost Google a lot of money. I remember my boss saying at the time, "So Josh, what did you learn from the X million dollars we just spent educating you?" 


<blockquote>_It's the kind of thing where you learn that canaries are good, and that 5 pm pushes on a Friday are pretty much always a bad idea, no matter how good your feature flagging framework is._</blockquote>




**What do you think is the number one mistake that’s made around feature flagging?**


<blockquote>_I think my biggest thing is if you are really thinking of feature flags as just “on” “off” switches, you are missing the real power of what they can do. _</blockquote>


To me the feature flag space is the parameter space that I get to explore to optimize whatever metrics that I want to optimize. If you are constraining yourself to this very limited boolean on/off space without strings, floats, etc. you’re putting artificial limits on how fast you can explore the space and about how all of the knobs at your disposal work.


<blockquote>_This will be the early mistake that I think a lot of people make-- they won't feature flag often enough._</blockquote>




**Can you share any tips for better flagging?**

I think what was most compelling for me at Google was the configuration language for feature flags was very rich, but not Turing complete. I don't think that configuration-as-code is a good idea for feature flags, because it becomes harder to test/validate, which slows down how quickly you can roll things out. However, the configuration language was like programming in the sense that you could define what we called “condition functions” that could be evaluated in the context of a request and used to adjust the values of the flags. So the logic was like a long series of “if” statements, where you could modify the resulting value either by overriding it or by addition, multiplication, or other custom operators.

The way it worked when I was at Google and working on the ad system was that the server binary was pushed weekly, so the only changes that you could make during the week were via experiments. Having that sort of richness of programming via feature flags allowed a lot more freedom and a lot rapid safer iteration between those weekly pushes. The same logic applies today for mobile apps, where you can only do releases via an app store, but you want to be learning what works much faster than that.



**How do you think feature flags play into the DevOps movement? Continuous Delivery?**

How would you do anything without them? 


<blockquote>_What does it mean to do DevOps without feature flags? It’s one of those things that doesn't make sense to me. How would you make mayonnaise without eggs? It's like, not really mayonnaise then. Which is good, because mayonnaise is gross._</blockquote>


I would be fascinated and somewhat horrified to have someone try to explain a feature flag-less DevOps set up. I don't know what would that look like.
****



**Are you seeing feature flagging evolving? If so how? And how do you expect it to change in the future?**

Not as much as I would like, broadly speaking. I'm not at Google anymore, so I don't know what the current state was when I left. The stuff they had is much richer than anything I've seen anywhere else, but to be fair, they were doing a lot of machine learning much earlier than anyone else, too.

I think feature flags need to find a way to strike the balance between configuration as on/off switches and configuration as Turing-complete programming language. That was the thing I felt was most compelling and powerful about the way Google did it that I've not seen anywhere else.


