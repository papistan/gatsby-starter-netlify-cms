---
author: andreaech
comments: false
date: 2016-08-30 19:46:45+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-the-process-of-category-creation/
slug: to-be-continuous-the-process-of-category-creation
title: 'To Be Continuous: Category Creation'
wordpress_id: 1054
categories:
- To Be Continuous
tags:
- Andreessen Horowitz
- cash consistency
- category creation
- CircleCI
- Cisco
- continuous delivery
- continuous integration
- Docker
- dogfooding
- Heroku
- IBM
- JSON
- market size
- Martin Casado
- microservices
- Microsoft
- Oracke
- SaaS
- VMWare
---

In this episode, Paul and Edith are joined by [Martin Casado](https://twitter.com/martin_casado), General Partner at [Andreessen Horowitz](https://twitter.com/a16z). The group discusses the deeply complicated and difficult process of category creation, with a special focus on technology infrastructure products_.  _This is episode #24 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.



**ABOUT THE GUESTS**







**Martin Casado **is currently a General Partner at Andreessen Horowitz. He was previously the cofounder and chief technology officer at Nicira, which was acquired by VMware in 2012. While at VMware, Martin served as senior vice president and general manager of the Networking and Security Business Unit.




**TRANSCRIPT**

**Edith Harbaugh:** What do you like about continuous delivery?

**Martin Casado:** I think that there’s a broader movement around continuous delivery that is really interesting, which is, traditionally, infrastructure and operations came from an independent group. My first job out of undergraduate was working on simulations code in a national lab.

I couldn’t control anything about infrastructure. I really didn’t have budget to buy a pencil. You get infrastructure, and you’d have some application to code, and you’d work on that application. We’d fiddle around with our MIG files or whatever, and that was pretty much it.


<blockquote>The cool thing about the broad movement now, and I think CI/CD is just part of this, is more and more applications, application developers, are actually getting responsibility for operations.</blockquote>


This is provisioning, this is delivery, this is deployment. That’s a big huge change in not only what technologies get created but who’s consuming it and why they’re consuming it. I think it’s actually one of the more interesting trends right now.

**Edith:** This would be a great time for you to introduce yourself.

**Martin:** My name is Martin Casado, and I’m a general partner at Andreessen Horowitz.

**Edith:** But you did stuff before you were at Andreessen.

**Martin:** That’s right. The quick arc, as I mentioned, I used to be a research scientist at Lawrence Livermore National Labs. I spun out of that, did my PhD at Stanford. My research was in networking, so I was part of the team that started software-defined networking.

I was there for four years, spun out of that, started a company called Nicira where we did software-defined networking. I did that for five years. That was acquired by VMware. I ran the networking security business unit at VMware for almost four years, and four months ago I decided to change and become a VC.

**Edith:** So you basically created a category. What drove you to do that? What made you decide to start something knowing that it was so hard?

**Paul Biggar:** You’re talking about software-defined networking? For the viewers at home, Martin roughly invented software-defined networking.

**Martin:** There’s a whole bunch of people contributing, but I think a lot of the original momentum came from my thesis. You know, I’m going to be totally honest. If I had any idea how hard it was, I never would’ve done it.

**Edith:** Really?

**Martin:** I think so.

**Edith:** I think you would’ve.

**Martin:** Well, maybe. But it would’ve been a lot more daunting. I came out of Stanford pretty darn naive, like, “This is going to be easy!” Now, nine years and tons of gray hair later, I just realized that, man, it was a battle. I don’t think I had one quarter that was easy. Everything was a battle.

This is the way that I think about it. If you’re an entrepreneur, and you’re going to do category creation, you basically just have two jobs, in addition to product development. And job number one is, there’s going to be some constituency out there you’re selling to, and that constituency, they wake up every morning and they think about all sorts of stuff, but they’re not thinking about your thing, because it hasn’t been created yet.

That object in the mind space, that object doesn’t even exist in their brains yet. The first thing you have to do is create that object. It’s like Leonardo DiCaprio at Inception. You go in, you’re planting an idea in somebody’s head. It has to become a thing,something people think about, something people know and integrate.

This is from nothing, and that’s hard. For us, it took 5+ years, and it touches every aspect of thought leadership such as analyst relations and technical conferences and broad marketing.

**Paul:** So the activities that you’re doing in that category creation are largely marketing and getting people to hear about the activity and learn about it?

**Martin:** I think so.I think maybe technologists will view marketing as this pretty shallow thing, but I think you’re exactly right. It’s marketing. But it is often very technical marketing, for example, in the guise of open source.

In releasing open source projects, you’re getting people to use it, you’re going to standards bodies, you’re going to conferences. It’s an incredibly technical thing, but in the end, it’s marketing in the sense that you’re actually creating awareness and a market.

The first thing that you’ve got to do as an entrepreneur is, if you’re doing category creation, nobody’s thinking about your thing. You’ve got to get them to think about your thing, which is a lot of work. In my experience, five to seven years.

Then the second thing that you have to do, which is just as much work, is then you have to attach a value to that thing. And I think we as technologists, there’s this kind of fallacy that we have where, “I’m going to create this new widget.” Let’s say I create the iPhone.

**Paul:** Everyone will know how amazing it’s going to be.

**Martin:** Exactly.

**Paul:** Just build it and they will come.

**Martin:** Yeah, there’s intrinsic value in my widgets. I take my widget, I put it on a sidewalk and someone picks it up. They’re like, “This is amazing. It’s worth millions of dollars!” And that’s totally not the reality.


<blockquote>The reality is people only see value if they exchange money and they’ve used it.</blockquote>


And if you’re doing category creation, how do people know what that value is? It’s a very difficult thing.

**Paul:** And when you say attaching value, do you mean monetizing? Or is there more to it than that?

**Martin:** I meant more the idea. Ultimately, this materializes monetization. Let’s say that you’re my constituency, and I’ve created this new widget. First I need to get you to think that this is actually a real thing. I’m going to call it a new phone. So, you need this new phone. First I need to convince you that you need the new phone.

Then the second thing I need to convince you is it’s worth tens of thousands of dollars to you because you need to mentally actually attach that value to it. And it turns out introducing new concepts don’t necessarily have value if they’re new concepts.

Normally, the value comes from, for example, an actual transaction. There’s a psychology around this. Or at least some experience with it, knowing that it’s going to, I don’t think you can just sit back to a couch experiment and be like, “Oh, I think this is going to save me money, therefore it’s worth something.” It really requires a lot of effort to make value.

**Paul:** So the category that I see being created, or the one that’s closest to me at least, is this idea of containers and Docker, and more specifically Kubernetes, the idea that there’s this cloud infrastructure over there. The way that I became aware of it is exactly the way you’re talking about it. There’s open source coming out there that you can use and you can hack on yourself. There’s talks up there where people blow your mind.

**Martin:** I think that actually this point, and certainly for all the listeners, I think this is one of the most salient points of this decade, actually, which is going to be a weird thing to say. At least an infrastructure’s the following.

In the past, how did we create mindshare and customer bases? Well, there’s this whole pmm function and this whole sales function. And if you look at the big enterprise companies, if you look at Cisco and IBM and Oracle, really their power is this function. They own the sales channel.

They have great relationships with the analysts, they’ve got great relationships with the customers, they’ve got certifications and the classes. So anytime they have a new concept, they take that concept and they cram it down the machine.


<blockquote>As a startup, it doesn’t matter how cool your technology is, the hardest thing is to actually penetrate that channel.</blockquote>


But when it comes to this new era of open source, now you actually have this hack that’s never existed before, where the buyer is shifting from an operator to a developer. Developers like open source, and you can actually create these concepts by getting open source out there and getting them to use it.

**Paul:** We’ve been talking about this sort of thing, just the idea that it’s bottom-up now versus top-down.

**Martin:** Not only that, it’s a totally different buyer that’s a totally different aesthetic. I don’t think developers care as much about analysts. I don’t think developers care as much about the 42-long sales dude with white teeth and the boat. I don’t think developers care as much.

**Paul:** They won’t even answer his call.

**Martin:** Exactly. About the channel, I think they don’t care about complex procurement processes.

**Edith:** Having sold software for a little bit myself, if you get into a bigger corporation, you still don’t start to run into that.

**Paul:** You get there, because the developers were first asking for it to exist.

**Edith:** The longest part of our sale cycle is you get bounced to procurement and legal.

**Martin:** Absolutely. I think this is the most important nuance of this argument, is exactly what you said. I’ve always maintained that open source and the developer is replacing marketing and pre-sales, not sales.

You get credibility to the account, you can get things to technical close and technical validation, you can get account pull. So it’s almost like filling the pipeline, getting the transaction done, I still believe. For a long time, you need to have a professional, direct sales force that will be in there pushing things for procurement.

**Edith:** It’s just a lot of work, because you pass the technical evaluation. They’re like, “Okay, go talk to procurement.” And to procurement, you’re a widget.

**Martin:** Right, but the good news is, now it’s possible. Where in the past, to get that much legitimacy, to get things to technical close, was very difficult. You didn’t have the certification, you didn’t have access to the buyer, you didn’t have the account rep to make the introduction. You didn’t have any of that.

**Edith:** That’s true.

**Martin:** And now you do, and now it’s just about actually going through the logistics. And you’re absolutely right, it’s hard, it’s baroque. I’ve called it tribal bloodletting. It’s all of that, but you can do it as a startup.

**Paul:** The thing that I think is really interesting is the converse of that. It’s that people who work in open source now are becoming actually incredible marketers. They don’t refer to themselves as such, but they have amazing social media presence.They build up tons of channels, whether it’s mailing lists or just Twitter followers.

**Edith:** It’s like everybody recreates marketing. Everybody’s like, “Oh, we don’t need marketing.” Then you’re like, “Well, what is this thing over here where you have an email list?” Oh, that’s not marketing.

**Paul:** It’s not marketing because I’m a developer.

**Martin:** I really think that those that know how to do this are some of the most valuable people in the entire industry because this is the new entree for products into customer bases. I mean, there’s another kind of potential pitfall here, which is, let’s say you’re using open source for marketing.

Now, there’s probably seven billion dollars have been invested in open source companies and only about a billion dollars worth of returns. I’m not sure if those numbers are true, but I hear them quoted all of the time. But the reality is, a lot of money’s gone into it and not a lot of money has come back.

The reason is because now, if you’re using open source to do marketing, you’re almost cannibalizing your sales motion. And so for a long time, the only open source model we knew how to work was the Red Hat model, which is a services company. Only Red Hat’s ever pulled it off. It’s been very difficult.


<blockquote>But another shift has happened in the last few years is people have figured out that actually you can use open source for marketing, but you don’t have to confuse that with your actual product offering.</blockquote>


And with the rise of services, you can actually use open source for customer traction. You can monetize the service, and when it comes to services, no discussion of open source or closed source. So I think that we’re actually starting to unlock viable business models where you use open source for marketing.

**Edith:** Who do you think does a good job of that?

**Martin:**I think GitHub is a great example, right? Git isn’t even built by GitHub. It’s the standard in Linux. But if you look at GitHub, it’s a very fast-growing company that’s based on open source, and so everybody knows about it because of Git.So Git is doing the marketing. And this is just one example, I think there are many.

**Paul:** It’s funny that you cite that as based in open source, because almost none of their stack is actually open source.

**Martin:** Exactly, it’s a service offering. That’s what I’m saying.

**Paul:** When you say service, you’re referring to software as a service, not service as in consulting?

**Martin:** Absolutely. I should’ve been more clear. The long-standing question for us, certainly since 1995, is how do you build an open source company that has the margins of a closed source software company? Because you’re open source, basically you become a service and support company.

What has happened in the last decade is exactly what you’re saying: people will realize that you can get account credibility and account traction, account knowledge, through open source.But then you can offer a back-end service offering as a service offering, and monetize that, and it’s often a closed-source stack on the back end of what you’re doing.

But you don’t talk about open source/close source as much with service offerings. It’s normally if you’re consuming something on-prem that you think about those things.

**Paul:** How do you feel about this? People who are building, let’s say CircleCI as a good model, but there’s a ton of them. Building something that’s a SaaS product, a hosted SaaS product, but that then sells to people who use it in their own VPC and pseudo on-prem sort of thing.

**Edith:** Oh gosh.

**Martin:** I come from this somewhat traditional world of selling enterprise software. In there, there’s this whole discussion, and I was part of this discussion, of is it on prem or is it off prem in general? And I think that you framed this question perfectly. I’ve realized that that’s a false dichotomy. It’s actually not the right question to ask. I think as a service, it isactually an operational model and a delivery model? It doesn’t really matter if it’s on prem or if it’s off prem.


<blockquote>I think that the days of selling closed-source software to companies is done.</blockquote>


But you can sell them services and you actually can sell them appliances. But if you look at appliances, appliances almost look like services. They’re boxes that have services, and often the upgrade is happening remotely, management is happening remotely.

I do think that the right model for these companies, I think CircleCI’s a great example of this, you have open source that customers use, you have a SaaS offering, but you also have an on-prem delivery offering as long as you don’t change the operating model, as long as it still looks like a SaaS model somehow, whether it’s a managed service or something like that.

I think as soon as it becomes shippable software, where you have to manage a heterogeneous set of environments, you have to manage all the day-two ops. It becomes unwieldy.

**Edith:** I had a really interesting discussion the other day with the VP of Sales from CircleCI and somebody from Microsoft. CircleCI was basically like, “We love that it’s selling on prem. It’s helping you.” Microsoft is like, “We’re trying to get off prem desperately.” So it was not the argument you thought was going to happen.

**Paul:** I think it’s probably because of how sensitive the IP is. If you’re talking about something like, well, documents are pretty sensitive, but the source code is very sensitive. And so people are not as happy to ship that off prem as we once thought was going to be the case.

**Edith:** Microsoft’s reasoning was, and this might be the way Microsoft had done it, is they have 10-year maintenance agreements.

**Martin:** We have, “If you have a problem, upgrade to the latest version and then we’ll deal with you.” I think that’s kind of what everyone has. There used to be this idea that you’d create a fork and then you’d backport things to that fork or the old version, or something like that.

I don’t know anyone who’s doing this sort of services, the SaaS with a managed to on-prem version that does anything but “the latest version is the version.”

**Martin:** If you think about it, having come from this world, anybody that’s shipping closed-source software, or even software in general, has so many hurdles to overcome that some of this that’s doing a sales offering or manage offering doesn’t have.

For example, heterogeneous environments. Everybody’s got a different hardware setup. Sometimes you have skilled administrators, sometimes you don’t. Now, when you’re dealing with distributed systems, a skilled administrator is really critical. These things, clusters, are hard to manage. Remote debugging is really hard. A lot of the debugging is happening on the site in these day-two operations where we’ve got existing tools, we’ve got to support all of those interfaces.

And then you’ve got the mother of all cash consistency problems. You’ve got 10,000 customers and everyone is running a different version. You have to maintain all those versions on the back end. It’s just a massive, massive disadvantage just from an operations standpoint for a company. So, if you can do it as a managed offering, just like you said, or a managed version, or a SaaS offering, you automatically have all of the velocity of that, and you’re not being weighted down.

**Paul:** It’s interesting that you’re talking about heterogeneous environments, because what we see is it doesn’t feel like there’s heterogeneous environments anymore. I mean, we’re selling. VMware is one environment, or there’s Amazon VPC is another environment. But it’s not like there’s 12 Unixes anymore.

**Martin:** That’s a super good point. I’m used to talking to hardware. And so in that case, and especially on the networking side, It’s just this eclectic collection of computer science past. Seriously, we go to these data centers, and then you’ll still have mainframes and you’ll have all the old Xboxes, you just have all this random stuff on the hardware.

I think one of the most exciting trends is exactly what you said, is actually we’re seeing unification on the software side. And I think that you can actually parallel what happened to consumer devices in about 2006. Do you guys remember GPSes? Actual hardware GPSes? In the 2000s, you’d rent a car, you’d get a hardware GPS. Most consumer goods were fixed-function, whether it was to play a game on your PlayStation Portable or it was a GPS or it was for learning or it was for health or whatever.

The iPhone came out as an ubiquitous software platform, and Android, you had two ubiquitous software platforms. And then small teams of software developers got to go after huge markets that displaced them. Waze is a great example. I think this exact same thing is happening in infrastructure, where in the past, the only standard interface was IP.

You had to put something in a box, or maybe x86, where you had to install it on bare metal. But now, if you look at software stacks on the end point, you’re absolutely right. This seems like they started to unify, whether it’s Linux, whether it’s AWS, whether it’s VMware, whether it’s Openstack, whatever it is. So it allows you to deliver functionality just entirely in software.

**Edith:** Yeah, I think the value’s just moving further and further up.

**Martin:** Yeah, exactly.

**Paul:** Especially with containers, because it’s a homogeneous environment. You get a certain kernel version, maybe, but I don’t know anyone who’s really cared about a kernel version in quite some time. So you build whatever software, and it runs on whatever operating system that you want, not whatever operating system the customer happens to have.

**Martin:** I just think it’s a really big deal for those that are doing startups. Everything that we’ve talked about basically is in support of small technical startups. For example, all of PMM is replaced by a technical function, which is open source. I think a small startup is going to be better at doing that, that’s technically focused.

Number two, instead of having to worry about a hardware supply chain, like wrapping things in sheet metal, which requires a supply chain management and putting things in shipping containers, putting things on boats, etc. You can just deliver stuff entirely in software. So it’s a great time to be delivering core functionality, especially infrastructure functionality in software.

**Edith:** They published an article recently on the stuff you had to do 15 years ago. My friend Andy was at Opsware. The stuff you had to do back then, you don’t do now. You don’t have to have an ops person on staff, you don’t have to buy hardware.

**Martin:** This is another really interesting trend, and I actually don’t understand the implications of this one. You’ve always had an operations layer. I’m a networking dude, so let me talk about networking. We used to put a bunch of stuff in networks. We’d do fault isolation networks, we’d do service discovery networks, we would do security in networks. And it seems like things are moving up to the application layer.

Things that are traditionally part of ops, things that were traditionally part of the infrastructure, compute networking and storage, are now application libraries,things like discovery, things like failover, things like load balancing, things like security.

And that’s a massive shift, because now it’s in the domain of developers. Now you’ve got more semantics. Now it’s part of the development process. And so I think that there’s implications on market fragmentation; it’s no longer a unified insertion layer. I think that we have to rework a lot of technologies. I think this is blurring a lot of traditional lines.

**Edith:** When you’re talking about the changing of technologies, what do you mean exactly?

**Martin:** I think a good way is just to talk about context. Let’s just talk about, say, security. In the past, you would have a box on a wire that would do security. And, say, a firewall. What does a firewall actually know? Very little, right? It knows IP pairs, it knows port numbers, maybe if you’re a fancy pants, you can look at the first 1,500 bytes of data and you can try and do some application analysis. But just seeing bits on the wire.

Now compare that to these new companies that are doing application-level security, where you’re actually part of the application. You’re running a Node.js. Your running is part of the Python runtime. You know everything. You know users, you know data, you know high-level abstractions. You can absolutely transform the level and type of security you can do, because you’ve got way more context.


<blockquote>It just feels like this is part of this broader movement where core networking is being done at the application layer, like routing and discovery and microservices architecture.</blockquote>


Security like I mentioned has been doing this. Storage has been moving up, certainly, to the object level. And I think that because you now have more visibility and more semantics, you can build deeper and richer things.

But I also think you get way more fragmentation, like per-language fragmentation. So as opposed to setting a box on a wire, where that sees everything, you’re now going to have one for node.js and one for Python, or whatever. I think we’re still grappling with the implications of this, but it’s really exciting to see this happen.

**Paul:** It’s interesting that when you see thata new software product comes out, and they’re an API, so they’re a HTTP API or a REST API. And they still say, “We support these three languages.” because they wrote client libraries for those languages. And people in the software industry still think, “We’re a Python shop,” or a Ruby shop or a Node shop, whatever it is. Even though there’s not necessarily a requirement for there to be that fragmentation, it’s still built into who we are.

**Martin:** That’s such a good point. And maybe this is just symptomatic of my past. It definitely think things are going micro services, and it’s more of a protocol. So it’s almost like we’re recreating IP. But we’re doing it like the JSON level, or something like that. And you’re right, this is actually totally language agnostic.

That said, and maybe it’s a good point, maybe we’re going to see some innovation of this space. That’s hit a lot of the movement that I’ve seen, too, of core infrastructure. Things like security to the application layer, aren’t language specific. A lot of the application security guys are basically having mechanisms that hook into the run times of these different languages.

And maybe you’re right, maybe what’s going to happen is basically the microservice’s framework becomes the next internet, and discovery and routing and naming and everything happens there, and you’re going to have these protocol-specific boxes that mediate these things. They speak JSON or whatever, and they can be firewalls at that high level.

**Edith:** I have a total jump shift of a question. You said, at the beginning, if you’d known what you know now, you perhaps would not have started the company. My saying is you can’t A/B test life. Do you wish you were still a PhD, and do you think a PhD has helped you with starting your company? I guess can ask the same question to Paul.

**Paul:** You go first.

**Martin:** If I roughly segment my life between 20 and 30, I was basically a core researcher. I was an academic and I was an engineer, and then 30 and 40, I did the company. And then now I’m doing investing, and I just turned 40. So between 20 and 30, I felt like that was leading up to doing this academic work.

The PhD was nice because I haven’t found any other times in my life where someone’s like, when I joined, my advisor went to go do a startup immediately after, and I still remember I sent him an email. I’m like, “What should I work on?” And his response was like, “Whatever you’d like.” And I didn’t know that that was a metaphor for PhD, which is that basically it’s the deep end, at least in my program.

It’s like, basically, do whatever you want. Being thrown into a vacuum and having to make some sort of form from the chaos means a lot. That said, it’s a massive investment of time that I don’t think there’s any commensurate payout afterwards. I think, at least in my experience, you have to view it as a self-enclosed system where I got the value out of doing it, but I don’t think having done it, it’s worth justifying the time. You can be just as successful as an entrepreneur and as a technologist and as a coder and as anything else without having the PhD.

**Paul:** I’m not sure I necessarily agree with that. I think that there’s a lot of value that you get coming out the end of doing the PhD. I agree that most of the value is from the time that you spend there, but even just looking at the social proof value, when I was trying to raise money, when I was getting my Green Card.

**Edith:** But I thought it was all about the podcast.

**Paul:** The podcast. Being Dr. Biggar is a lot easier than not, I find.

**Martin:** I think that these things largely depend on your personal arc, for sure. And I think I’m just sensitive to mine. When I did graduate with my PhD, I got a faculty offer at Cornell. Now, clearly this is something you don’t get without a PhD, so in that sense it was very helpful. But what I immediately did is turn around and I started a startup. If I look at other founders like Sanjit Biswas of Meraki who’s now doing Samsara. The guy didn’t do his PhD, I think he’s a way better entrepreneur than I ever was, and I think he’s hugely successful.

**Paul:** I had a funny experience where I was meeting this guy who worked at Google, on compilers. I did my PhD on compilers. And I had done my PhD because I had looked at this site called Compilerjobs.com,and it was all, “You need a PhD from a name-brand compiler school.” I remember this stuff.

So, all right, I’m going to do my PhD. I work in compilers. And then I was talking to this guy, I was like, “Oh, where did you get your PhD?” And he’s like, “I don’t have a PhD.” And it just blew my mind at that point, that maybe there was a thing, some other path. His path was working on open source since he was 18, and then at 22 he got hired to be a compiler editor. It’s like, oh, I could’ve done that instead. That would’ve been a much better idea.

**Martin:** Yeah, I think there’s just a selection bias here, too, which is interesting. In my experience, often the best developers didn’t finish college. But I think that the reason is is just because the job market really is a Darwinistic system, and I think that if you have this adverse selection of, “You don’t have a degree,” I think that is much more difficult.

The people that managed, one of my core engineers that I worked with for seven, eight years who’s super instrumental to the product, never had a college degree. Actually multiple of them didn’t. These guys often become principal engineers or whatever, but they do it just through sheer skill rather than, you know.


<blockquote>I think for some people, a PhD is super valuable as an experience to do. I think how you use it depends on your personal arc and what you need to get out of it. But I definitely don’t think it’s necessary to be a great entrepreneur, to be widely successful.</blockquote>


**Paul:** I noticed that you can split PhDs into people who are roughly the most brilliant people I’ve ever seen and people who are complete idiots. And there’s these two camps, that some people do it because they love it and they’re amazing, and some people do it because they’ve nothing else to do with their lives, and they can’t do a job, and actually anyone can really get through a PhD. It’s hard work more than anything.

**Martin:** That’s so true.

**Edith:** I was giving advice to a dude from my college. He was a programmer and he really loved machine learning. And so he was like, “Should I go back and get a PhD?” And my advice was, “I don’t think you’ll make anymore money. You might make less, even, because you might get pigeonholed. But if you really love machine learning, go get your PhD in that. But I don’t think you’ll make much more money.”

**Martin:**I wouldn’t, unless you want to be a professor or even want to join core research, I wouldn’t do it for future prospects. I’d do it because it’s actually one of the few times in your life where it’s just like, “Think really big and probably impractical, and do something amazing.”

**Paul:** You have four to six years to do what you like, just make sure it’s good at the end.

**Martin:** That’s right. And it does. And listen, it feels good to crawl out of that cave. When you finally see the light and you’re pale and you’re malnourished and whatever, but you’ve crawled out.

**Paul:** I regard it as being very similar to raising a seed round. You have some funding to do something, and you kind of thought you knew what it was going to be, and you might be totally wrong.You might need to pivot six times before you hit something good.

**Edith:** That’s funny. I went back the other day and looked at our angel funding deck, and it’s basically kind of the same.

**Paul:** Yeah, but you kind of knew what you were doing. There’s a lot of people who start off doing something and then end up doing something wildly different. If I had built a pitch deck for CircleCI on day one, it would’ve been vastly different to what we actually shipped six months later.

**Edith:** I mean, CircleCI seems pretty comprehensive.

**Paul:** The first thing that anyone saw about Circle was that it was for web apps, and then we added iOS after it, so now you can run a large amount of stuff on it. But when we started, we were building this CI for everything, so it was going to be CI that ran your on-prem machines, and it did performance testing.

I was working at Mozilla beforehand, so I was looking at replacing what Mozilla has. There was going to be all sorts of, “You could add your 3,000 machines to our something.” And we might’ve ended up in the same space or in the same place as where we are five years later, but the thing that made us successful was that it was really, really good at web apps.

It was like, and this is how we pitch it, if Heroku had built CI, this is what CicleCI would be. And that is why we took off. And when I look at people who did similar things, there’s that Jenkins company, CloudBees, that no one loves, because it’s just Jenkins. It’s Jenkins plus we added some cloud to it. Everyone loves the, “Oh my god, you click one button and it just works,” or you can spend two days setting the whole thing up.

**Edith:** Did your company end up where you thought it was, where it had started?

**Martin:** Certainly not from the seed. It’s funny, I actually pointed that the Series A deck recently, and for the bulk of the deck, we actually executed pretty much every step exactly when we said we’re going to execute it, which is actually very rare.

There’s a very related, but somewhat tangential point, is I was talking to a good friend of mine recently who has done multiple startups. He was an employee at multiple startups, and he’s thinking of going to a new startup. This is a senior engineer, a really experienced guy, and he told me, “Listen, when I select startups now to go to, I always make sure they’ve gone through one pivot.”

And I said, “Why is that?” And he said, “Well, because the number one thing that I’ve experienced that kills startups, it’s you do your basic diligence, and you’ve got reasonable funding, is basically some issue with the founding team.”


<blockquote>You don’t see these things materialize until you actually go through some stress, and the pivot is a pretty good stress.</blockquote>


To put just some numbers on that, if I go across an average swath in a general VC portfolio, about 70% of the companies will have a founder already gone, which is a really striking number, if you think about. These guys have equity that they’ve probably vested in that’s no longer part of the company, and so forth.

I actually think that most companies will go through pivots. There’s stories about that. And I think it’s actually for general hygiene. I think it’s not a bad thing, because you’re going to go under a ton of stress anyways. And it’s interesting that pretty experienced startup engineers will actually look at that as a good sign. It’s a different way than we normally view it. because I was like you, we were lost in the woods for about a year from seed to A, but from A on, we executed on plan.

**Paul:** Why were you lost in the woods?

**Martin:** I think a number of things. I think we were incredibly naive. It was a research group that spun out of Stanford. This was also in the wild and woolly days of 2007, where you’re just basically turning down money all the time,and for some reason you think you’re so awesome.

We had this “We’re going to do this super general platform.” We were going to boil the ocean. We had this, basically an architecture, but no product. It was this classic early days. We knew there was a problem to solve, but basically our solution was an architecture not a product, which was a mistake. Or at best, a platform but not a product.

Then 2008 hit, and that’s when we had to grow up. You guys remember. There’s just bloody carcasses still quivering everywhere that you walked. Sequoia released a “RIP Good Times” deck. Everybody was going out of business. We stayed at 12 people for about a year and a half, just because funding was so tight. And that really sure forces you to focus at the end of the day. You can’t raise forever, and at that point you couldn’t raise at all.

**Paul:** So you got it together before you raised again?

**Martin:** I remember we were in a tailspin for about a month. I wasn’t really sure. I could pitch a broad vision, but I couldn’t, and this is when you know you’re a mistake. If you can pitch a broad vision on how the world’s going to change, but you can’t pitch specifically what product’s going to do it, it’s basically if your pitch is “Here’s a litany of use cases we can do with our general platform,” you’re in a bad spot.

So we were in this tailspin. I remember staying up all night one night and we just sat down. We’re like, “Okay, this is the bet we’re going to make. And it’s hard.” And then you make the bet, and yeah, we penciled it on out.

**Paul:** You got the bet right.

**Martin:** We got the bet right.

**Paul:** And was there a close second that would’ve been the wrong bet?

**Martin:** Absolutely. It’s hard to talk in the abstract without talking specifically about what we did, but I’ll say one thing, and this is not specifically about the product. At the time, the conventional wisdom was the only way that you could build networking was to wrap it in sheet metal.

They’re like, “The only way these guys know how to buy is sheet metal. The only way the channel knows how to sell is sheet metal. So you need to sell a box.” We even had some of our investors, I remember one in specific. I was off of Sand Hill in Rosewood talking with a round of investors. You’re like, “Martin, you’re a bright kid.”

**Paul:** Those conversations.

**Martin:** Yeah, that’s right. Pat the pet on the head.

**Edith:** Nobody ever calls me a kid, a bright kid.

**Martin:** Edith, I think you’re a bright kid. But in my heart of hearts, this is going to have to be wrapped in a box. And what we were trying to do was trying to sell a network functionality of software. And to this day, I believe that we never would’ve had the outcome that we had, which it was one of the largest exits ever in enterprise software, I think it’s actually the largest on multiples of revenue, is


<blockquote>if we would’ve decided to tie it to a box, I don’t think we would’ve had a company.</blockquote>


**Edith:** I love all the stuff you’re saying about disrupting enterprise software, given that you came out of enterprise software. What do you think is the role of the CIO in this future that you paint?

**Martin:**CIO, to me, is a business executive function around information systems. I think actually, to me, what’s even a more interesting question is, “What is a CTO?” I think it’s one of the most ill-defined titles in all of Silicon Valley, and the job description’s ill-defined.

**Paul:** I think a CTO is a founder that was there at the start and got lost and has founded new technology.

**Martin:** It could be, right? But so it depends.

**Paul:** I hear a CTO from post-Series B. I’m like, that’s probably what you do.

**Martin:** It could be, but here’s what I’ve seen for CTOs. I’ve seen CTOs that are basically architects. It’s 100% inbound function, but it’s not a developer. It’s an architect. I’ve seen CTOs that are VPs of Engineering. So they basically manage engineering teams. I’ve seen CTOs that are kind of like that crazy research guy that still has his foot in academia and probably isn’t doing any direct product stuff.

I’ve seen CTOs that are basically doing project management functions, so they’re the conduit between the customer and the product. I’ve seen CTOs that are outbound sales, who are basically super SEs. This is the person that brings things to technical close; he’s the most credible person in the room.

And I’ve seen CTOs that basically function as CEOs. They do all the technical strategy, they do the building out. So it’s kind of funny. In Silicon Valley, there’s the two highest jobs in the startup are the CEO and the CTO. CEO is incredibly well-defined. We have books on CEOs. I’m in Andreessen Horowitz, but Horowitz, I thought, wrote a phenomenal book, “The Hard Thing About Hard Things.” Nobody has actually sat down, and said “This is what it means to be a CTO.”

**Edith:** It’s the same with COs. This is what we should do. We should actually write a blog post.

**Martin:** Seven chapters for each of those different jobs.

**Edith:** Not to belabor, but you’re certainly a technical guy. What made you decide to be the CEO instead of the CTO?

**Martin:** No, I was CTO.

**Edith:** You were.

**Martin:** I was CTO of Nicira, but I had an outbound business function. I was an architect. I wasn’t aligned with the product. I was basically aligned with the go-to-market sales motion, a lot of the technical strategy around open source.

**Paul:** So what did the CEO do?

**Martin:** The CEO did P&L, growing, setting culture at the internal, a lot more of what you’d think a COO did. And he’s a phenomenal, phenomenal CEO. He also did a lot of the pricing and packaging. He was our VP of Marketing beforehand for Palo Alto Networks.

**Paul:** So where did the product function answer to?

**Martin:** Product rolled up into the CEO. Product rolled up into product management CEO, and then the engineering rolled up in the CEO. When we went to VMware I became the GM, and then everything rolled up to me, and then I was doing both. I was basically, I mean I had a CTO, but I was doing the evangelical stuff.

But it’s very interesting. I would argue that in category creation, market category creation, the most important function is the CTO function, if it’s business aligned. Because, go-to-market is so technical. It’s so technical. You basically need that voice and that understanding of the ecosystem, as far as the business function.

But again, it’s such an ill-defined thing, that sometimes you’ll have these CEOs that are highly technical that are actually, I would consider, performing as CTOs. You’ll have a strong technical CEO and a COO. So the COO does all the stuff internally.

**Paul:** This a New Relic sort of thing.

**Martin:** For example, yeah. That’s a great example.

**Edith:** Travis with CircleCI made a really good point at his Gluecon talk. He thinks the danger that companies run into is that they think it works great at the very beginning, but then when they get bigger, they don’t realize that they’re designing for companies that are not themselves.

**Paul:** Right. I think dogfooding is one of the most dangerous things.


<blockquote>In particular I notice that what you’re good at when you’re a small company are the things that you’re going to be bad at when you’re a larger company, because you think that you just know how to do this stuff.</blockquote>


And you don’t hire for it. Maybe if the founding team is particularly good at writing software or product managing or writing blog posts or something like that, they’ll be really late hiring marketers or product managers or whatever it is they need. Because it’s built in and they don’t realize there’s a separate function that does it.

**Edith:** The best advice, well, he gave me many good pieces of advice, Andy Sylvester said, “You’ve got to get leverage.” Because I was like, “Oh, I’m pretty good at marketing. I’ll keep doing it myself.” He’s like, “No, you need to hire a marketing person.”

**Paul:** Right, and that marketing person, for a year or two, won’t be as good as you.

**Edith:** But now that person is great, and I have my time free to do other things.

**Paul:** The relationship to dogfooding here, I think, is that when you build the product for yourselves, you don’t invest in the function of talking to your customers. And you don’t invest in the function of prioritizing what your customers need, because you know what they need.

**Martin:** We all know what they need, because we’re using the product ourselves. If you make mistake of conflating, basically, feature and product understanding with dogfooding, I think it’s a mistake.

I think dogfooding is a good way for QA. Like, okay, we run it internally to surface bugs that happen over normal usage. But to actually think that that will actually drive product roadmap?

**Paul:** Well, it’s great on day one, and it stops being great at day, like, 400.

**Edith:** Did you dogfood your own stuff at your company or how did you?

**Martin:**I actually think this is an interesting narrative to pull, and actually you and I were talking about this earlier, which is, yeah, we dogfooded a lot. We’d build it and we’d dogfood it, but the 100% point of dogfooding was not because we’re going to know what features to build next.


<blockquote>The point of dogfooding was to try and actually run it for real and see what problems materialize, maybe some basic operations problem. If something happens, what kind of debugging support can you put in?</blockquote>


I think that’s a legit kind of feedback. But there’s this a very interesting question that’s adjacent to this that I think is worth exploring, which is let’s say you’re doing category creation.

**Edith:** Continuous integration.

**Paul:** No, see, I was the opposite at category creation. Category’s built, it was there, everyone needed it, and what we were doing was bringing it to the cloud. And that was a movement that was underway already. We had to do no category creation, we just followed. It was wonderful. Highly recommended.

**Martin:** Which is ideal. It’s the right way to go, man. Category can barely walk, right? It’s like Edith’s 100-mile run of the Bear.It’s just the most grueling, brutal thing, but let’s say you decide to go ahead and embark on this Odyssian saga of category creation.

There’s this question of, okay, so how do you determine the next set of features? And the reason why this is an interesting question is because, well, if you think about the existence of the product, it’s purely prescriptive. The people don’t even know it exists, since it’s totally prescriptive. You’re like, “You need this.”

And so of course, the first features that you come up with, and because you’re doing category creation, it takes a while. The first set of features almost certainly you’re going to come up with, you’re going to say, “This is what you need.”

At some point in the maturation of the product cycle you’re going to want to get feedback. It’s a very interesting discussion of when that is. If you’re too early, generally, and you’re using the sales motion for product feedback, you tend to build a lot of one-offs and you become a contract engineering job. If you do it too late, the market can mature in a different direction than you’re going, because it’s going to mature and then you can actually get feedback.


<blockquote>Staying very close to the product/market fit in a maturing market is probably the most critical function for an organization to do.</blockquote>


In my experience, I always align that with PM to do that.

**Edith:** I think the key, to talk about my own experience, is to be able to do it very quickly, because if you’re doing a release every year, the stuff you’re aligning with has already changed.

**Paul:** And now we’re back to continuous delivery.

**Edith:** That’s the title of our podcast. And Paul, thank you very much for wearing your LaunchDarkly T-shirt.

**Edith:** My point is that you’ve got to be constantly in touch with your customers.But the thing is is that customers move, too.

**Martin:** For me in category creation, there is some point where you’re going from being purely prescriptive. By definition, category creation is prescriptive, because nobody’s thinking about your thing. You’re going from purely prescriptive. All the early product releases are going to be prescriptive, because again, they’re not even sophisticated thinkers.

For the first three years, you’re the most sophisticated thinker of your nascent category. So you’ve got this newborn category you’ve created, we’re going to call it the Edith Product. You’re going to be the world expert in the Edith Product, whatever it is.

But at some point in time, you created a pull-based market where you actually will walk into customers that are more knowledgeable than you because they’ve surveyed multiple competitors in the space, and they thought deeply about it.

They know their use cases better than you do. And once it becomes a pull-based market, you’d better be plugged into the customer needs. So you’ve got to be very sensitive. You’re starting out being prescriptive, here’s “SnakeOil 2,” or whatever it is, to here’s what you need and what you want, and we’re going to give it to you.

**Paul:** So my perception of category creation is that you get to own the category when you’re done.

**Martin:** Yeah.

**Edith:** That’s the hope.

**Martin:**I don’t think a category exists without competition. I just don’t think it exists. I think the only way to have a category is if there’re multiple voices, multiple people players. And so that’s one of the things that you actually track. I think if you created the category, sometimes you can maintain ownership, but very often that’s not the case. Very often it gets away.

You can almost argue, like for example, virtualization was created by IBM or something like that. Though for x86 virtualization, VMware did it, but I think there’s many cases where categories were created by one company but then another company out-executed them, I really do.

**Edith:** So how did you do that then?

**Martin:** It was very interesting, our arc. The category that we are still creating, but I think is largely there was network virtualization. It wasn’t SDN. SDN was this high-level architecture thing, but network virtualization is “Here’s a software, here’s what it does.” And now there’s many, many companies that do that.

**Paul:** Quickly define network virtualization.

**Martin:** Network virtualization means, let’s say you have a physical network in the data center. So you’ve got a physical network in the data center. Traditionally, you’d have a bunch of stuff in that physical data center. You’d have VLANs for L2, you’d have L3, you’d have policy routes, you’d have ACLs, you’d have all of this stuff.

What network virtualization says is, “You know what? Just build a really simple physical network, say, just using IP. Just all three.” And then all of the other stuff we’ll make into software abstraction, just like a virtual machine.

So instead of creating a virtual machine, you create a virtual network. It looks just like a physical network from operations and management, but it has the flexibility of a virtual machine. You can create them dynamically and move them around and grow them and shrink them and whatever. And it’s 100% software, so it just runs on the servers.

Think about a hypervisor for the network. Now you can create all four through seven services on demand, you can scale them on demand, you can move them between data centers, and it addresses a bunch of use cases. So what’s interesting is, I think we did a lot of the early original work, but then you got multiple players in there.

Now, if you ask people today who’s the leader, I think they would say, a toss-up between Cisco and VMware. And now Cisco did a lot of the original work as well. But here’s the good news. If you’re doing category creation, and you’re a challenger, to be lumped in as a competitor with the incumbent with a $40-billion market or $40 billion market or $20 billion market or whatever it is, is amazing.


<blockquote>We’re very, very happy to be shown side-by-side to Cisco. And now actually there’s quite a bit of collaboration between the two companies.</blockquote>


So yeah, I do think that we emerge as one of the top players, people who consider us one of the top players certainly would consider us the pioneers, but as far as the absolute leader, I think that you’d get different answers depending on who you ask. And that’s not necessarily a bad thing. If you’re going from zero to some number, every bit of credibility is upside.

**Edith:** Just like Paul, you talked about your Docker article and how people were hurt that they were left out.

**Paul:**I wrote an article on Docker and I mentioned a bunch of companies. And, satirically, I was making fun of everyone involved. But the people who didn’t get mentioned were annoyed: “I’m very sad. We’re working hard to be part of this Docker space, and we’re not.”

**Martin:** So are you going to write another version of that article that includes everybody?

**Paul:** I heard about this because I wrote a follow-up that mentioned a few more companies,and one of them wrote to me and said, “Oh, you know, I was really left out.”

**Martin:** Like a Dante-level thing, where you’re going to have multiple layers include everybody in it.

**Paul:** I think I’m done with that particular. I’ve beaten that horse to death.

**Edith:** Well, speaking of beating horses, it was great to have you over. Do you have any final thoughts on startups, infrastructure, DevOps?

**Martin:** First off, it was great to be here. Thanks so much for the time, I enjoyed the conversation. The only thing that I think I would use as a capstone comment is thatI do think this is the most exciting time in infrastructure in our lives, just because of all the change we talked about. I really do.

I do think that all of the advantages,


<blockquote>every time you have these big shifts, these big transformations, you always have new challengers unseat incumbents and market sizes grow. And we’re seeing both.</blockquote>


The market size is growing, and you’re going to see new challengers. It’s never been more weighted to technical startups ever, like as far as becoming credible.

So it’s a great time to have this conversation. It’s a great time to be in Silicon Valley, and if there’s one thing that you want to know as you start your companies, try to understand whether you’re actually creating a market category or not. Because everything after that will follow. So, anyways, thanks so much, guys.

**Paul:** Awesome, thank you.

**Edith:** Thanks for coming over.


