---
author: mattdel
comments: false
date: 2019-09-09 19:17:29+00:00
layout: post
link: https://launchdarkly.com/blog/test-in-production-a-panel-discussion-on-progressive-delivery/
slug: test-in-production-a-panel-discussion-on-progressive-delivery
title: 'Test in Production: A Panel Discussion on Progressive Delivery'
wordpress_id: 194276
categories:
- Continuous Delivery
tags:
- custom targeting rules
- progressive delivery
- service mesh
- Solo.io
- test in production
- user targeting
---

At our July Test in Production Meetup in San Francisco, Christian Posta, Global Field CTO at [Solo.io](http://solo.io/), and Adam Zimman, VP of Platform at LaunchDarkly, fielded questions about testing new software features in production. The session followed educational talks Christian and Adam gave on [chaos engineering with service mesh](https://launchdarkly.com/blog/chaos-engineering-with-service-mesh/) and [progressive delivery](https://launchdarkly.com/blog/the-daughter-mother-in-law-challenge-a-case-for-progressive-delivery/) respectively.


<blockquote>"...the old enterprise machine model [is] where you have very low trust with anybody else in your organization, and everything is completely siloed. And you hand off over walls and stuff, and you separate out people's responsibility for the actions that they take. Versus the...let's learn, let's try something new [approach]. And if it fails, that's fine. We're learning, right? And then we're exploring new ways to deliver value to our customers and make money." - Christian Posta, Global Field CTO at [Solo.io](http://solo.io/)</blockquote>


Watch to learn more about how service meshes and feature flags differ, how to plan for failure, and how to tailor feature rollouts to best suit your customers' change tolerance. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://youtu.be/ieF293ZM9GY[/embed]

TRANSCRIPT:

Andrea Echstenkamper, Director of Marketing at LaunchDarkly, Moderator: Thank you both for your talks this evening. Just wanted to take this time to ask you a few questions, have a little discussion, and take questions from the audience. But I kind of want to kick it off with, Adam, in your presentation you had the meme that people know about "test in production." I guess I'd love to hear both of your histories about that term, kind of how you thought about it before, and how you think about it now.

Adam Zimman: So, interestingly enough, that exact meme for me holds a lot of meaning because when I was running a large scale service at VMware, my team was responsible for hands-on labs at VMworld. And one of my developers as a joke actually put that as the screensaver for 500 user terminals in Moscone Center that were set up for individual lab stations. And we actually had a bug in our user interface because it wasn't adequately tested. And so during opening day of the conference, there was about a 30-minute window where every single screen in the entire room went to that image.

Yeah. It wasn't funny at the time. But you know, I think it for me then it had a very different connotation in that it was this notion of kind of cowboy development of kind of individuals that didn't take testing seriously, or hadn't been in situations where the production product mattered. And that made it very real for the individuals on my team. And as I started working more and more in the dev tools space, started to realize that teams that were running large scale production environments well, teams like Google, teams like Netflix, teams like AWS, they, by their very nature, they were doing tests in production because they realized that it was an imperative to the success of their production environment. And so it was something that I started to think a lot more about and the reason why you [Andrea] and I started this meetup, right?

So I think that it's something that has definitely started to transition. And as I mentioned in my talk, I've definitely seen the transition with our customers as well.

Christian Posta: Yeah. And so for me, I guess it was when I was working for a big bank. And we deployed once a quarter, and the way we did that was we said from Friday afternoon until Sunday morning, once a quarter, you took off the whole weekend from your family. And you sat on a phone call and chat rooms and you did your deployment. And invariably doing that deployment would break something, and there would be emergencies, and fires, and all of this stuff because they were trying to deliver three months worth of functionality and software that we had all been working on, and trying to coordinate with each other, and all ram it into production at exactly the same time. And from there, so obviously I was like, this sucks, but that was just how it's done.

From there I went to go work at Zappos.com. And we worked very closely with the folks at Amazon and used their tooling. And the release process at Amazon was 180-degrees different than what we were doing at a big bank. And I thought, oh, there is some hope, there is maybe an answer to some of the pain that we felt every three months on the weekends. And I dug into what Amazon was doing, but it was very Amazon specific. So once some of the technology like containers and communities and some of these cloud-native tooling things came out and started to come out, it started to resemble ... I was like, oh my God, that's exactly ... that's what Amazon had eight years ago.

And once I saw Envoy Proxy ... I saw Matt Klein give a talk with Envoy Proxy about three years ago. I thought, that is something that gives you a level of control over the network traffic, so that you can separate out deployment and release like you [Adam] mentioned. And that is incredibly, incredibly powerful. And so from there, for the last three years or so, I've been working with the enterprise customers to help them understand exactly what that means. Because I don't know if they really understand. I don't think they've had the ah-ha moment, or at least some of them have had the ah-ha moment about what that really enables some. That's what I've been working on.

Andrea: So the next question, I just want to ask about, it seems like in the last five years or so there's been really a proliferation of feature management companies, as well as service mesh. I guess, why now? What's changing and why now?

Christian: I think with the realization that organizations, or at least like again, my spin, I'm talking about enterprises, they realize that technology can be a differentiator for their business. And as they look to adopt. So they look at Netflix and they look at Google and they look at what these internet companies have done, and they're trying to go off and do that. So some of this technology is coming out as being open-sourced, and it's becoming more available, and coupled with their desire to figure out, okay, how do we take this hundred-year-old company and become more agile, and all of this stuff? There's legitimate market pressure for them to do that because they've seen like Borders and, you know, Blockbuster and, you know, you can go on and on and on about these institutions that are being disrupted by technology companies. And they don't want to be the next one.

Adam: Yeah, I mean, I think that I totally agree with everything that Christian said. I think the other aspect of it that I took away from the time that I spent at GitHub was also just the GitHub phenomenon. Where seeing how, you know, I think that relates to the open-source movement, but making it much more accessible. Making it something that was a much more communal and really kind of helping to accelerate the building of these tools but also making it much more common for folks to have a way to adopt them and get onboarding support, or try them out or things like that. And really kind of move forward. Coupling that with the notion of people feeling or realizing that if they didn't move forward, then somebody else was going to do it for them. Right? And so that's kind of like the Uber phenomenon or Lyft phenomenon of like disruption.

Andrea: So you spoke about kind of this daughter, mother-in-law dichotomy. You know, this idea of a digital native and someone that expects changes on more of a seasonal basis. Are there examples in your own product in LaunchDarkly, or Solo, of how you think about that?

Adam: Yeah, so I think that, for me, as I've spoken with a lot of our customers and prospects, companies that are looking to move in the direction of either feature management or just to more generally in this, kind of the enterprise term of digital transformation. But looking to basically modernize their developer toolchain, their workflows. There are a lot of constraints that are applicable to that same problem statement, that are not necessarily kind of generational as you know, kind of, I made it personal. Right?

You know, one great example is regulation. And you think about organizations that work with unions, have worked with a number of government organizations that have union employees or union workers, and in their union contracts now it is not uncommon for them to actually have language about the number of times in which the software that they're required to use can be updated, as well as the training requirements around updates to software. And so if the organization is using some type of tool or platform that updates at a cadence that is beyond those restrictions, they say, I can't use this, right? Or they put unreasonable restrictions on that vendor, that provider, that are very difficult for them to accommodate.

Christian: And I think for Solo, we sell to large organizations that, for them to adopt some of our technology, they have to be at a certain level. Let's just say, like in terms of ... I'll give a simple example. They need to have a particular version of Kubernetes, or a minimum version of communities, for example. And sometimes, they want to adopt the later technologies and the newer technologies, and they want to operationalize them. But for them to do that is such a phenomenal, or like, Herculean effort to get to the next version and to upgrade and to keep current. That sometimes will affect us because then we don't, you know, we have to wait for them to upgrade and so on.

And then the other part of our product stack where we're going to build more of a SaaS version, obviously that gives us the ability to deliver features more quickly and leverage some of the techniques and methodologies around progressive delivery and reducing the risk of making changes and so on. Because enterprise users, enterprise organizations, they're also very resistant to moving too fast. So yeah, that's something that we definitely deal with very much.

Andrea: Do you have any questions for each other before I open it up?

Christian: I think we're very complementary in what we're doing at our different organizations.

Adam: I would concur.

Andrea: That's beautiful.

Christian: Yeah.

Andrea: Okay. Well, if you think of any. How about folks from the audience? Oh, and we have a mic out there. Over here.

Audience question: When is it appropriate to use your technology in an early startup?

Christian: So, in my opinion, you're going to need traffic control. Whether it's a monolith or a ton of microservices, or whatever. At Solo what we're trying to do is help people take that transition at the speed that they're able to take that transition. So some of the more forward-looking stuff that we're building right now that depends on service mesh, that wouldn't be applicable to a small environment like that. But we do have an API gateway built on Envoy proxy, which would be much more suitable to that sort of environment.

So we're looking at it as a series of stages in a series of iterations to get toward, if you need to, right? If you need to. And in my opinion, I would say if you guys are small teams starting out with the monolith, like, that's exactly the right way to do it. Don't over complicate it by doing the microservice and bringing all this other stuff. Go at the speed that makes sense and doesn't take on any unnecessary complexity for that.

Adam: Yeah, I think that for us at LaunchDarkly, we have tried to create some entry-level offerings for small organizations that are kind of modestly priced and give you the ability to start adopting the methodologies around building with feature flags and building with feature management. The kind of main thing that we've done for a startup your size is that we have an entry-level plan that literally has just a shared login account, right? If there are just two or three engineers, you don't need the kind of granular access control or audit logging that you'd have a need for when you get to an engineering team of 20 or 30 or hundreds or thousands. Right? And also from a volume perspective, you know, like trying to think about like, you're not going to be doing a whole lot of flagging.

You're not going to be doing ... You've got three people that are going to be pushing to production. You don't have nearly as much to keep track of. But getting in the practice of doing it is something that we've seen a lot of teams that are represented by individuals that are coming out of organizations that have strong feature flagging practices. They've said, "look, I could build this myself, but is that where I want to be spending my time? Or do I want to spend my time on the product that I'm actually going to be kind of extracting value or delivering value for?"

Audience question: What are the challenges in taking the delegation to the last mile?

Adam: Yeah, it's something that we have talked a lot about, and I think that it is going to be somewhat dependent upon the types of services or applications that someone's offering. You know, you brought up Gmail, or you know, kind of the Google work suite is a great example where you can go into the Google Labs interface and you can, effectively, it's user-facing feature flags. And that's actually how they're implemented. Where you're turning feature functionality on and off for your personal account. I think that is actually a great way to build products. And I think that being able to use LaunchDarkly in that capacity, it's not something that we see a lot of at this point in time, but it's definitely something that we want to get to a place where we can scalably support that.

Right now what we encounter is, more often than not, people are really looking for the kind of core infrastructure use cases, or being able to do the management from the company perspective, as opposed to pushing out that delegation all the way to the end-users. But ultimately, I do agree with you, that I think there is a future where that kind of end-user delegation is perfectly appropriate. The other way that you can do that is you can actually use user attributes that people can change the configuration on. And then those attributes are just detected by the feature flags. So that's the way in which we encourage our users to do it today. So that gives them one kind of layer of removal, or comfort, for them to make sure that the change of the actual code path is being kind of held back, you know, to the company. Whereas, the user can change kind of just an attribute or a key value.

Audience question: Is there a relationship between security and chaos engineering?

Christian: Yeah, that's a good question. So one of the things I mentioned in the slides is that there are these dark unknown areas that exist in our system, whether we care to admit it or not, right? Security is one of those areas. And to go through and assume that different parts of the application, let's say they have different ... or they trust each other at levels that you expect, but then going in and proving that they do, or finding ways that they may not, or the reverse, right? So I think chaos experimentation, or more just, that's why I don't like the term. It's more exploratory experimentation, and that absolutely includes security and penetration testing and validating trust across the network and those types of things. So yeah, absolutely.

Audience question: What is the synergy between feature flags and service mesh?

Christian: I was hoping somebody would ask that question. So I'll give my first stab at it. So when you're making changes to your software, that by definition means you're going to roll out new binaries, or new configuration for your applications. So one example that I've seen used is when you make a change to a stateful service, right? And that stateful service, maybe you're also making a change to the schema in the database, or something, right? Now as you make that change, and you roll out that new binary, you want to deploy that, and then either run some smoke tests against it or run some level of a percentage of traffic, or a cohort, or traffic against that new deployment. And you can use the service mesh to control the traffic to be able to do that.

Now once you get some traffic going in there, you might then want to flip the feature flag and say, okay, let's actually turn this new feature on. I mean, we made the code changes, we have the flag off, we put it out into production. It looks good. Now let's actually turn the feature on. And some of those that are then going to see, let's say version two of the schema, and some of them will see version one, and so on. And so there's probably a lot more handful of these types of examples where it makes sense to both control the traffic as well as progressively open up that functionality to the users.

Adam: Yeah. The analogy that I've found successful in kind of visualizing this is, you use a service mesh to be able to kind of build a new building, and deploy the new version of the building. And then you use the feature flags, those are your lights switches inside. And you can kind of turn them on and off based on wherever you place those switches. So per floor, per room, whatever you need to do. And it gives you varying levels of granularity, right? You can have the ability to be able to say, hey, I want to test out this new structure that I've created, as opposed to this new feature that I want to be able to control.

Audience question: There seems to be much more empowerment for engineers?

Adam: I think that the two experiences that you've had, I think both kind of exist in the industry, obviously. But I think that the notion of having a few folks with the keys to the kingdom, as you put it, is very common for older companies, and companies that have not yet built the kind of stability in their infrastructure, and the practices around continuous delivery in that type of methodology. A lot of times there is a fear aspect of things breaking. I think that this is something that Christian talked about of like his experience at the bank, or even just the idea that you don't know what's going to happen. You build these services, and your expectation when you build them is that they're pristine and that they will always stay up, and they will always be there.

And with that notion, like if you're not actually constructing infrastructure and services and designing them for failure, and what I mean by that, is that you are actually building things so that you're not just building them and saying, oh this is going to stay up all the time. Because you know, one of my favorite quotes from Charity Majors is, "All infrastructure fails." It's just, it's true. At some point in time, there's going to be a stress that you didn't account for. And so the question is, are you going to build it so that it fails gracefully, and it has some notion of what those failure modes are going to be? Have you actually planned for them? Have you tested them? Have you validated those tests that it does what you expect it to when it fails?

Or, are you just going to cross your fingers and say, "no, I'm just gonna make sure it never fails." Right? And I think more and more companies, especially with more and more companies putting their products and services out on the internet where there is so much that goes on that we can account for. That they are confronted with this requirement from a user perspective of clean failure modes, of understood failure modes, and being able to actually have services and products that fail gracefully. So I think the experience that you've had is this transition where you've moved to a company that, Coursera is obviously, they're built around internet delivery, right? That's the only way they function. And so they've had to make sure that their failure modes are thought through, and that they have the ability to accommodate for those.

Now a byproduct of that is that they feel a lot more confident failing, because it's not about whether or not you fail. That's eventually going to happen. It's, how long does it take you to recover, right? The metric that's been increasing in popularity from a operations team perspective, or from a DevOps methodology perspective, is mean time to recovery, or MTTR. Right? This is like, how long does it take me to recover from some type of failure or outage, as opposed to, kind of this notion of five nines of service availability, or things like that. You know, ultimately, if your ability to recover from an incident is not well thought through and orchestrated, then the number of nines you have isn't going to matter.

Did that answer your question?

Audience speaker: Yeah, that's very helpful. Thank you.

Christian: And I was just going to add that, it's also ... so it's a very organizational, as part of their DNA even, right? Some of the larger companies have been around for a while. They've figured out, at one point, they figured out how to make money, and make a lot of money. Right? And so they build their organization in such a way to continue to turn that crank to make money. And you do that by optimizing for efficiency, and you segment people into their one little spot and where they don't have to see the big picture, they work on their one little thing. And they build an engine that's able to churn out money, right? But some of these other companies, they might be churning out money, but they're less, you know, a machine, and they're more organic. And they're ability to adopt a change, and the market around them is fundamentally built to be not a machine. It's to be adaptive and reactive, and change.

And so from the old enterprise machine model where you have very low trust with anybody else in your organization, and everything is completely siloed. And you hand off over walls and stuff, and you separate out people's responsibility for the actions that they take. Versus the, you know, let's learn, let's try something new. And if it fails, that's fine. We're learning, right? And then we're exploring new ways to deliver value to our customers and make money. So organizationally the two things are also quite different. And so the enterprises are trying to figure out, how do I become more like this organism that is able to adapt and survive, decentralize and "high trust" and all that stuff? That's a huge struggle that they're going through right now.

Audience question: Do feature flags create too many combinations?

Adam: Yeah, I mean, I think that you raise an interesting point with the kind of delegation model, and the kind of number of options that are there. And I think those are actually two separate challenges. I think that the delegation model does not necessarily require that you have an infinite, or you know, even a large number of options that you are allowing access to. It could be just a standard Boolean true or false of, is a feature on or off. And that could vary for various end-users, or customers, or in your case universities. But from a code perspective, that's literally, you've just got two code paths, and then you've just defined users going down code pathway A or code path B. And so it's fairly simple. The other aspect that you're talking about of creating a multitude of variants, a multi-variate option for all of those different end-users, or universities.

While it's something you could do, it's not necessarily something that I would encourage unless you had a really well-defined need for it. This is kind of like the problem of the kind of N matrix problem that so many packaged software vendors used to face of, you know, what revisions did they support and for how long? Right? And what you don't want to do is as a SaaS service, you don't want to create that same common editorial matrix. Like that would be horrible. Right? And so I would never advocate for that. I think that the idea of supporting two versions, or maybe even three versions, to give people some more flexibility. Or one thing that we've seen a lot of our customers do is they'll have a ... We allow for hierarchy in our flags. So you have the ability to do kind of like roll-up features where you say, either you're getting the new stuff when it's available, or you're not. And you're getting that at some type of regular cadence.

So it could be quarterly, it could be annually. And then you're getting that kind of, here's all the new stuff that's come out. And the nice part about that is it's kind of like being on, you know, if you've ever joined like a beta program from like Slack or Apple, or something like that, where there are people who are just like, yeah, blow up my machine, I don't care. You know, but I want to see the latest and greatest features as soon as they're coming out. And then there are other people who are just like, no, I just want to be on the stable release. Right?

And so you can think of that as the kind of stable release model where you're saying, okay, look, I'm going to push stuff out on a regular cadence at the pace that my engineers are building. Right? And therefore you're getting updates or new feature functionality or new workflows on a daily, weekly basis, whatever it is. Or you say, I want to see the new stuff, but I want to accept it when I'm ready for updating my documentation, for doing training, for making sure that I'm not in the middle of a sales cycle, or I'm not in the middle of my peak tax season. You know, whatever your requirements are that make it so that you want a predictable user experience, you can account for those.

Does that make sense?

Audience speaker: Yes. Thank you.

Adam: Of course.

Christian: And having those control points from the edge of ingress all the way down into the depths of your code, and all the different combinations and so on that you can get, presents a pretty interesting opportunity for being able to explore what people really want. Because you give them the choice to name all these feature flags. Users probably don't want that much choice, but it'd be interesting to put things out in front of them and see how they respond. And then build models and experimentation models that try to learn what people might want, and then validate that. So I mean that becomes a really interesting space for showing people what we think they want and then letting them tell us what they really want.

Adam: Yeah. It's that feedback loop notion, right? Where you're using these control points as a mechanism to be able to guide your iterative development, right? You think about, a continuous delivery model, or even Agile to a degree, where you may have large-scale epics that are split up into multiple sprints where you have an end state. But the idea of Agile was that you still have the ability to be able to alter based on the feedback of those individual sprints. And imagine if you are getting that feedback not just from your development team or from some type of internal organization, but you were able to incrementally ship, like in a continuous delivery model. And all of a sudden you're getting that feedback from your users, either from targeted user segments or from percentage-based rollouts to, kind of randomized user segments.

Christian: Thank you all for coming out.

Adam: Yeah. Thank you very much.

Andrea: Thanks so much.
