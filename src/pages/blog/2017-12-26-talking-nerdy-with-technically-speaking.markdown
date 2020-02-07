---
author: Kimh
comments: false
date: 2017-12-26 21:01:58+00:00
layout: post
link: https://launchdarkly.com/blog/talking-nerdy-with-technically-speaking/
slug: talking-nerdy-with-technically-speaking
title: Talking Nerdy with Technically Speaking
wordpress_id: 2124
categories:
- DevOps
- Feature Management
tags:
- Agile Midwest
- continuous delivery
- Developer Advocate
- feature flags
---

Our own developer advocate sat down with the Technically Speaking podcast at the [Agile Midwest](https://www.agilemidwest.org/) conference in St Louis, MO. They discussed what a developer advocate is, the LaunchDarkly feature management platform, and how teams use feature flags.


<blockquote>“Decoupling that deployment from the activation of code gives people so much more security and reduces the risk of deployment. I think a lot of reasons people resist continuous deployment is the fear that they could break something and not be able to fix it in a hurry. So with this we’re saying, ‘Deploy all you want, activate when you’re ready.’” - Heidi Waterhouse</blockquote>


Check it out to hear how companies like Microsoft and GoPro are using feature flags to dark launch, do internal testing, and use feature flags as kill switches.

[embed]https://soundcloud.com/teamdaugherty/heidi-waterhouse-live-from?in=teamdaugherty/sets/agile-midwest-2017[/embed]

**TRANSCRIPT**

**Zach Lanz:** Live from St. Louis, Missouri, it's the Technically Speaking podcast, brought to you by Daugherty Business Solutions. Get ready 'cause it's time to talk nerdy on the Technically Speaking podcast.

Welcome back in, Technically Speaking. We are talking nerdy today. We are talking all day. We're live at the Agile Midwest Conferences here in beautiful, beautiful downtown St. Charles, Missouri at the St. Charles Convention Center. I mean, I can overlook the river right out the window. It's picturesque. Today we have quite a collection of some of the most forefront on the agile front lines and thought leadership bringing you some content and their perspectives. This episode is no different because today we have Heidi Waterhouse. Heidi, welcome to the podcast.

**Heidi Waterhouse:** Thank you. I'm excited to be here.

**ZL:** Listen to your adoring fans.

**HW:** My adoring fans.

**ZL:** We might have to shut the door so they leave us alone. So Heidi, you are in town from Minneapolis, coming all the way from Minneapolis, correct?

**HW:** Yes.

**ZL:** Just for the conference?

**HW:** Just for this.

**ZL:** You had your talk earlier today and I understand that you had a couple technical snafus.

**HW:** Oh well, I think it's not really a presentation if something doesn't go a little weird, but I did get to talk about the things that I cared about so that worked out.

**ZL:** You are a developer advocate at LaunchDarkly. From what I understand, it's a company that specializes in feature flags. Tell us a little bit about what a developer advocate is, what you do there, and a little bit about LaunchDarkly.

**HW:** A developer advocate has three different roles that we serve. The first is I go out to conferences like this. This is my third this month. I have two more to go and I have five next month. I talk to developers about ways that I could improve their workflow and make their lives easier. I also spend a lot of time listening to developers and figuring out what it is that they need so I can take that back to my team and say, "Hey, there's this unmet need the developers have that we need to look into." The third is recruiting. I meet a lot of developers and I can say to them, "Hey, we have this opening for a full stack developer in Oakland." They're sometimes interested in it. Midwesterners seldom take us up on, "You could move to Oakland."

When I say LaunchDarkly and feature flags, what I'm talking about is LaunchDarkly is a company that provides feature flags as a service. You wrap your code in a little snippet of our code, connect it to the SDK and then you deploy the whole package and it sits out there like Schrodinger's code, both the live and dead, until you flip the switch to turn it on. Decoupling that deployment from the activation of code gives people so much more security and really reduces the risk of deployment because I think a lot of reasons people resist continuous deployment is the fear that they could break something and not be able to fix it in a hurry. With this we're saying like, "Deploy all you want, activate when you're ready."

**ZL:** Just generally I guess, I think you touched on it a little bit, but explain a feature flag and what that does.

**HW:** A feature flag, or a toggle, or a feature management, it's called a bunch of different things, is a way to turn a feature on and off from a central command. We work with Fastly and we have edge servers that help people to do this. Imagine you deployed a feature that say gave you the ability to do holiday snow on your webpage, like CSS that made your webpage snow. Well, it turns out that has a conflict with some browsers and you're crashing people's browsers. You want to be able to turn that off instantly. We like to say that you can kill a feature faster than you can say, "Kill the feature." It's about 200 milliseconds. All you have to do is flip the toggle and the feature turns off almost instantly for everybody, instead of having to deploy again and hope that you get it right this time and didn't leave anything in.

**ZL:** You mainly work with companies large and small, I would imagine, that have a need to be able to turn those features on and off. Are there any great success stories that you'd like to share of being able to prevent an issue before it happened, or turn it around before customers even knew?

**HW:** We work with Microsoft and they do a lot of dark launching and sneak the features in so that they can do what we call canary testing, where you test with a small percentage of your population. But we also worked a lot with GoPro to be able to let them develop in their main line and do internal testing. Then, when they were ready, they pushed out their new version with no problems. Not a lot of people tell us when they have to hit the kill switch. We can see it in the logs, but I don't want to call anybody else because it's uncomfortable to have to say, "I deployed something that was bad," but it's not as uncomfortable as it is if you have to say, "I deployed something that was bad and it took forever to fix it."

**ZL:** Your session today was a choose your own adventure interactive. I love that concept. I love games and I love just the interaction in a session like that. Walk through the concept there of how the choose your own adventure maps into this idea of deploying in a dark manner and the feature flags and things like that.

**HW:** We have a little mascot, an astronaut named Toggle. I created an adventure for Toggle where you can choose how you want to get to a planet based on different routes, like which ones are safer, or which ones are faster, or which ones are most scenic. If you think about the way you can sometimes get a map to show you like, "Don't put me on any freeways," that's sort of the way that I designed this talk. This is the first time I've used the Twine gaming platform to design a talk. It turned out my CSS is really rusty, but there's a lot of good help out there, so I got through it. It was really interesting to be able to say like, "Hey audience, pick which direction you want to go. Let's talk about the thing you're interested in. I've created 60 some slides of content, but the path through it is unique every time to your experience."

**ZL:** How did they react? Which routes did you go?

**HW:** Unsurprisingly, the first route that we took was development. We talked about canary launches, which is the small launch, and we talked about multivariate flags. You could say, "I want to launch to 10% of the people in Germany." We are basically doing access control lists for you product. You can slice and dice your audience however you'd like. Then, I really love this concept, I got it from Fastly, the albatross launch where you have a legacy client that's very important to you that you want to keep happy, but you also want to keep your code base moving forward, you can switch them over to the older code base and keep your mainline moving forward without having to actually split your lines, split your code instances.

**ZL:** Well, awesome. Also, my crack team of researchers also dug up a little bit. It looks like outside of maybe the workplace, you are maybe an aspiring designer or seamstress.

**HW:** Oh yeah. I sew 100% of the clothes that I wear to conferences because I am really tired of dresses that don't have pockets. If you wear a mic pack you have to have a belt of pockets. I just do all my own sewing and I find it super satisfying to make something tangible after a long day of software, which is a little fuzzy around the edges. Also, it means that I get to do tourism shopping. I just came back from New York and I honestly have a dedicated fabric suitcase.

**ZL:** Wow. Now it's all coming out.

**HW:** My regular check on, roller board size suitcase fits in the big suitcase. Then I've come back from, oh, Tel Aviv or Australia or London, with a second bag, essentially, full of fabric. In fact, the dress that I'm wearing right now has fabric from Australia and London.

**ZL:** Wow. It's a trip around the world for your clothes.

**HW:** It is. It's really a nice reminder that we aren't just here to do technology but also to experience the places that we go.

**ZL:** Yeah, absolutely. Do you have any places in mind for this trip? Have you eyed any places?

**HW:** Actually, I've never been to St. Louis before, but I don't have a lot of time on this trip. I actually have to leave in a few hours.

**ZL:** Oh, that stinks.

**HW:** Yeah, it's very sad.

**ZL:** Well, hopefully you get back to the airport in time and no delays there.

**HW:** Yeah, no. It's only a couple minutes so it should be fine.

**ZL:** If people have heard about either LaunchDarkly and are curious, want to hear more about these feature flags, it sounds like a fantastic offering. I don't know who wouldn't be interest in something like that, to be able to control your launch a little bit and pull stuff back if disasters happen. If people want to get in contact with you, or with the company, what's the best way to do that?

**HW:** They could write me, Heidi@launchdarkly.com, or you can find us on Twitter @LaunchDarkly, or you can find me on Twitter @WiredFerret.

**ZL:** WiredFerret.

**HW:** I know.

**ZL:** What's the story behind that name?

**HW:** Well, it turns out that I am both excitable and high strung, so yeah. Anybody who's seen me at a conference party understands.

**ZL:** Got you. Do you bite?

**HW:** I don't. I don't. That's definitely against the code of conduct.

**ZL:** Yeah, because I mean, that's the MO on ferrets.

**HW:** It is. It is. We had ferrets for years and they were terrible sock thieves. Whether or not your foot was in the sock, they were going to steal it.

**ZL:** It was gone. Well, I appreciate you stopping by and giving up some of your lunch hour. I know this is high priority time, so I appreciate you coming on, sharing your perspective. It sounds like your presentation went great despite a couple technological glitches. I hope you have a good flight back and thank you for taking some time out and sharing your perspective with us today.

**HW:** All right. Thank you.

**ZL:** Thank you for listening to the Technically Speaking podcast. Get involved with the show by following us on Twitter @SpeakTech, or like our page at Facebook.Com/SpeakTechPodcast. If you have suggestions or questions related to the show, or would like to be considered as a future guest, send feedback and inquiries to hey@speaktechpodcast.com. I'm Zach Lanz and thank you for listening to The Technically Speaking podcast.
