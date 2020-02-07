---
author: Kimh
comments: false
date: 2018-04-09 17:39:29+00:00
layout: post
link: https://launchdarkly.com/blog/the-customers-wont-be-happy-how-atlassian-rolled-out-a-large-scale-ui-change-for-confluence-cloud/
slug: the-customers-wont-be-happy-how-atlassian-rolled-out-a-large-scale-ui-change-for-confluence-cloud
title: 'The Customers Won''t Be Happy: How Atlassian Rolled Out a Large Scale UI Change
  for Confluence Cloud'
wordpress_id: 2478
categories:
- DevOps
tags:
- Atlassian
- Confluence
- feature management
- testing in production
- user feedback
---

At our March Meetup we visited Atlassian's new offices in Mountain View. Aaron Gentleman, Software Development Team Lead at Atlassian, shared how his team actually tested in production when they rolled out ADG3 to Confluence Cloud.


<blockquote>

> 
> <blockquote>There was sort of three main concerns. There was: is it ready in the first place, is it actually ready for customers to start using? What's the impact going to be like, not just for them but actually for us and sort of what does it look like when it's complete, when we say we're done. What's the definition of done actually look like?</blockquote>
> 
> 
</blockquote>


Watch his talk below to learn more about how the team addressed these concerns throughout the testing and rollout process. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://www.youtube.com/watch?v=Sa7NhDMUcVs&feature=youtu.be[/embed]

TRANSCRIPT

And I've been at Atlassian for about two and a half years now. More recently, been here in the States at Mountain View for seven months or so. And I'm really here to talk to you today about one of the ways that we actually tested in production. Some of the customers didn't like it.

More specifically, I'm actually gonna be talking about how we rolled out ADG3 to confluence clouds, so can I get a show of hands, who actually uses the confluence cloud product today?

Alright, around 15 to 20 percent of the crowd. That's good. Can I get a show of hands who used it before we brought out the design change. Alright, about half of that again. And how many of you were frustrated with the actual rollout. Like the actual UI change. Alright, only two. That's you know, narrowing down so it's alright.

What I really wanted to bring up is the fact that established users are actually really frustrated with big changes like that. So for those that are unaware, what we really did was take out some big key navigation components from the top of the application that everyone's used to clicking every single day, like a create button, a dashboard button, a profile icon and we completely ripped that out and put it to the side of the product and a lot of them have gone "why are you doing this? This doesn't make any sense, I can't use the product at all." The feedback from our design team was "well this is awesome, you just gotta get with it".

That was useful feedback from both customers and design but it still wasn't very nice for the customers themselves. For those that really aren't aware what the product used to look like was that slide on the left which is really tiny to use. You probably can't actually see it. But what we can see up the top on the left is the old navigation components. We had an app switcher, we had a create button and a search button. It's all there really easy to use and then on the right hand side we have the new UI. What you can see is what we call a portable navigation experience. How you navigate around the whole product and other products. And then on the right portion of that sort of more content directive related to what you do on a day to day basis. And the design team have a really good reasoning as to why they've done this but it was very painful for a lot of customers originally.

So what I wanted to talk about when I actually get this back. Yep that's good, is how we actually roll this change out to production for customers.

Rolling out and testing production, we had sort of, we had a lot of concerns but there was sort of three main concerns. There was: is it ready in the first place, is it actually ready for customers to start using? What's the impact going to be like, not just for them but actually for us and sort of what does it look like when it's complete, when we say we're done. What's the definition of done actually look like?

When we ask the question "Is it ready?" We ask, what we're trying to actually ask ourselves is "Was this change something that we ourselves would be willing to actually accept and take on?" In our particular case the answer was yes. Internally we'd actually been using it for about three months internally on all of our development sites. We were very conscious of the limitations that it would actually bring. We wanted to make sure that when we do roll out we don't actually roll out to stuff that people aren't ready for.

One of the other questions is what does that actual percentage rollout look like? Some of our considerations were previous tests that were done on customers. Before rolling ADG3 we'd started a new trial for a single page app in the product. So for those that use ADG3 the whole application, well not the whole but the general application is single page application but before that we'd started rolling out an experiment where it was the UI but single app. Those customers weren't too happy about receiving that change because again it was a big change and they weren't happy. But then we wanted to make sure that when we started rolling this out, we don't actually roll that change out again to those new customers that had already received the previous experience. In LaunchDarkly we actually created sort of a prerequisite group, so an actual feature flag in LaunchDarkly with a set of all those customers that got that old change and made sure we set a prerequisite in LaunchDarkly to say "do not serve this up to these people at all until we're actually really ready for it".

One of our strong considerations was also the definition of done for the customers. So we needed to make sure that when we rolled out those changes, our definition of the customer was actually not an individual user, it was the full site. So, everyone that actually collaborated and belonged on that site got all the same experience from it at the same because what you don't want is someone that's, suddenly gets a UI change and then all of a sudden goes "How do I find anything? How do I use this?" And then they look to the person sitting next to them and they're still seeing the old version. "What the -? How come you've got this and I don't have this? That's really frustrating. You can't even help me do my day to day work." That was a really strong consideration for us when picking the appropriate key for out percentage rollouts.

We also wanted to make sure that, actually that was about it for that.

We wanted to make sure, another consideration was who gets what version. Who should be getting the change? Should it be new customers, should it be existing customers? What we actually did was we purposely started rolling out to existing customers first but then when we got to a certain threshold of happiness and completeness from a feature point of view, we then started looking at how we roll this change out just for new customers. Our actual rollout pattern hit one hundred percent for new customers before it even hit all of our legacy, existing customers.

By the end of the actual project, we were rolling out at about ten percent every single week from a rollout percentage to see how often people actually got the change.

Another question was "What's the impact?" Are we fucking the customer? Which is actually one of the elastic values which James just brought up and talked about before. It's don't fuck the customer. So that's a really strong consideration for us is we know that these changes are going to hurt people but you know sometimes it's for the greater good, but really you've got to, there's a fine line between "she'll be right, they'll get used to it" versus "no this is actually not right, they're not going to get used to it, they're going to leave us." That was a really strong consideration.

Another consideration was if they do run into problems with this, how can we help them? How can we make sure that this change is easily rolled back for them, or for the entire user base. And another change was that, how can we support the actual support load? Given that we're already a product that's been around for a while, one of our primary considerations was what's the impact of the change? Can this change, wait sorry. I apologize I've already gone through that bit.

I'll jump into the fucking with customers because that's sort of the one that gets all the quibbles from everyone but you know. As I was talking about, how we test huge changes in production. We had a bunch of research that showed that this design and this layout was actually going to be better for users in the long run, but for existing customers that wasn't really the case and people were like "No, I'm really used to this, you're just completely stuffing up how I actually do my day to day work." We needed a way for them to be able to opt out of that. One of our considerations was actually do not roll out this to people that have actually selected to opt out. We controlled that by the context that LaunchDarkly lets us provide so that when we actually contact and you know check LaunchDarkly's features page for that customer, we provide a whole bunch of context and then in our actual feature walls we say "for this context, don't serve this to a customer who has said don't give it to me". That way, the customer can still be happy and still get done what they want to do while we can still progressively roll out in a non micro managed way. We don't have to do it for every single user.

Another consideration was how an we help them. So if a customer was truly negatively impacted, we needed to be able to roll it out and support, or able to actually just be able to go in, add the customer's site ID to a list of prerequisites and bang, the whole site doesn't actually get it any more. That was really important for customer support to be able to really help customers when the problem happened.

And one of our last considerations was, can we handle the support load. So rolling out changes and testing changes in production isn't just an engineering feat and isn't just a growth experiment feat and isn't just for design and marketing. It's really also support and one of our, because checklists wasn't really ready from an engineering point of view. It's is support ready to handle this increased load. So when we first started rolling out, we had massive spikes in support because feature wasn't complete. It wasn't as thorough as it was previously and there are a couple of edge cases that we couldn't just catch when testing in spec and testing locally in development.

They were quite quickly fixed with the front end and what we've got in confluence we can actually roll out change in a minute. They were quickly, really quick to actually recover and fix the problems for the customers but the support load and the support impact is still actually there. That was a really strong consideration for us every single we time we sat down and had a meeting. Should we increase it to 5 percent? Should we increase it to ten percent, twenty, fifty, a hundred? So, just when you start testing something in production just keep in mind it's not just an engineering decision. It's a decision for the whole team and that includes potentially your support if you've got peep support.

So, lastly we get to "Are we done?" We've rolled this feature out to production. We're a hundred percent, we're done right? There's nothing else to do. That's actually sort of, not the way that we consider it. We consider it, it's only just started now. We're actually here, we're a hundred percent. That's actually now the base experience for customers. What's next? For us, in confluence, we're actually experimenting right now with a bunch of navigational changes for customers because not everyone likes the change in how they can actually navigate pages and page trees and stuff like that. That's one of the experiences that we're trialing right now.

We're also trialing a newer navigational experience on the side so that people can actually experience both the new elastic home offering as well as easily get to Gero if they use Gero and other products. We've actually also asking the question, was it the right choice? We got to a hundred percent of customers back in August which is nearly six or over six months ago now. And all the data is showing that okay yes it looks like it's generally the right choice. There are a couple of holdouts that are still not quite happy. But over time we feel that with the right level of communication with them and the right feedback from them, we can actually get the right answer from them.

But it was also the right choice technically. So, this was also a force in change for us to re-envisage how we do the front end in the product. It was a really big engineering feat to change what was an old legacy code based build with Jquery and technology before Jquery and all the way up to backbone and luckily not end killer but. I don't mean that facetiously.

But we actually got to re-envisage what that front end code base is and what the whole delivery pipeline is for the front end and now we're actually reactor based code base in the front end and it's a single page application for the majority of user experiences and across the board the users are a lot happier with performance of the product right now. Outside of initially loading the page, navigating to other pages is a lot quicker than it ever used to be.

One of the questions that we didn't really expect and sort of hit us in the butt and really knocked us for a six is "What needs to be cleaned up?". So we'd gone through, we'd been making these changes, we'd been building it since October 2016 and what we didn't expect is the fact that okay it's behind feature flag, we can actually turn this on and off by LaunchDarkly production without any problems at all. It's actually with a single click of the finger, you can actually turn it off or turn it on. But developers weren't actually using that experience because again it was behind a feature flag. One of our, one of the things that sort of we weren't expecting was the fact that we'd actually have to go back through our code base, make that the default experience and then actually fix our continuous integration through our CI to actually make sure it's also testing that new experience which is actually the default experience for customers.

There was almost as much effort pointing out that old experience in our build pipe, within our build pipeline and our tests and local development as it was actually rolling out that feature in the first place. So that's something, that's a strong consideration that anyone that wanted to do this level of testing in production should keep in mind to a degree.

What else I wanted to talk about was a couple of other ways that we at Altassian also test in production
experiment on people. We get a lot of flacking on Twitter for that. Some people are like "why are you doing this experiment on me? Why are you doing this experiment on that?" And it's not, we don't intentionally mean to upset customers but we've got teams that are actually dedicated to trying and improving integration experience between all of our products and sign up experiences and making sure that when you buy Confluence, the first email you get sends you directly to Confluence and those kind of things. They're actually trying to evaluate this. That's another way that we sort of test in production, those are little growth experiments.

We also use it to control risky changes. Sometimes there's changes in the product that we can't control, well not we can't control, we can't test effectively in development or in staging. And the only way we can really effectively test this is when we really get to production. We come up with a design, we undertake the underlying product and have a flag and when the feature flag's turned on for that customer, they start running that new experience and then when it goes bad, we get so many pages and then we wake up at 3 in the morning and fix it.

That's another way that we use that. We also, like I mentioned before, we are still using it to actually build on and improve the new UI that we've brought to Confluence today. We're working on changing the space navigation for customers and working on a better happy experience so that the UMUX instead of NPS to also check people's happiness.

I did want to actually go into a couple of gotchas that we did run into when sort of, not just using the LaunchDarkly but just rolling out feature flag type changes to customers in production. So basically having multiple code paths in your product. One gotcha or one really cool thing to know about with LaunchDarkly is actually the dev console. For those that are unaware, in LaunchDarkly when you actually set up your group in LaunchDarkly you can actually use the dev console to see a stream of all feature flag activity. So people that are actually requesting flag x, flag y, flag z. If you pause that and actually click on any one of those records, you can actually see the associated context with it as well, which helps you easily sort of drill down into going "okay, I want to target these specific people. I want to start target these specific features." And that helps you sort of correlate between what your product or your service is sending to LaunchDarkly versus what your feature flag should be set as in LaunchDarkly as well.

Another sort of gotcha is using prerequisites. One thing that's bit a lot of people in the butt in the past is when you, you might create a feature flag with a prerequisite based on another feature flag and then later on in the future that feature flag is no longer relevant so you delete that one, but if that is a prerequisite for another flag all it does is remove that entry but then that feature is, has a blank prerequisite. What that ends up doing is causing the feature to serve up the false condition or the default condition so just be careful of that when actually using and removing prerequisites.

With percentage rollouts, make sure that you actually click the advance button. You can't really see it in the screenshot there but down the bottom after you've actually done your percentage rollouts, you've chosen 20%, 80% or whatever. If you're multivariate, you've got a big breakdown there. Make sure you check the advance, make sure you're actually rolling out on the expected keys. For us at Atlassian, or at least Confluence our key was actually based on the users versus for ADG3 we wanted to actually roll out on a site by site basis. We had to make sure we chose the appropriate actual percentage rollout based on sites rather than on customers. Just check that advance button and make sure you're actually doing the right thing there.

And again the last one was really about builds and devs. I think I touched on it just before we started. If you're actually building these multiple code paths in your product, make sure you're testing them and making sure you've got a plan that's part of your definition of done to actually clean that code path up when you're happy with it either being removed or being the default.

That's it. But the last thought is really please think of the customers when you're actually rolling out changes. Thank you.
