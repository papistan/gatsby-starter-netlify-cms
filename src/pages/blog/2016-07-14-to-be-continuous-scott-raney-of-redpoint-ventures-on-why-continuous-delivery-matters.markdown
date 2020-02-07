---
author: andreaech
comments: false
date: 2016-07-14 19:51:15+00:00
layout: post
link: https://launchdarkly.com/blog/to-be-continuous-scott-raney-of-redpoint-ventures-on-why-continuous-delivery-matters/
slug: to-be-continuous-scott-raney-of-redpoint-ventures-on-why-continuous-delivery-matters
title: 'To Be Continuous: Scott Raney of Redpoint Ventures on Why Continuous Delivery
  Matters'
wordpress_id: 978
categories:
- To Be Continuous
tags:
- Amazon AWS
- continuous delivery
- developers
- Dropbox
- enterprise software
- github
- Jeff Bezos
- Lyft
- microservices
- on-prem
- Redpoint Ventures
- Scott Raney
- Sean Byrnes
- stripe
- TripIt
- Twilio
- Uber
---

In this episode, Edith and Paul are joined by [Scott Raney](https://twitter.com/sraney?lang=en), Partner at Redpoint Ventures. Edith, and Paul hear from Scott why continuous delivery matters in modern software development. This is episode #21 in the To Be Continuous podcast series all about continuous delivery and software development.

<!-- more -->This episode of To Be Continuous, brought to you by Heavybit. To learn more about Heavybit, visit [heavybit.com](http://heavybit.com/). While you’re there, check out their library, home to great educational talks from other developer company founders and industry leaders.




ABOUT THE GUESTS







**Scott Raney:** Scott focuses on cloud computing, on-demand and open source software, enterprise infrastructure and mobile platforms. He’s especially interested in the rise of distributed computing and developer-facing businesses. Scott serves on the board of Twilio and has been involved with Redpoint’s investments in adap.tv, Cloud.com (acquired by Citrix), Cyanogen, Expensify, Heroku (acquired by Salesforce), Jumptap, Platform9, RelateIQ (acquired by Salesforce) and Stripe.






**TRANSCRIPT**__







**Edith Harbaugh:** Hey, so what do you like about Continuous Delivery?

**Scott Raney:** Continuous Delivery, I think, really for me is an interesting manifestation of a broader trend which is about the ability for organizations today to move faster than they ever have before. It’s really one of the things that help drive nimbleness in software development which, ultimately, as more and more businesses are run through software allows companies to be more flexible, and quick moving, and as you said nimble than ever before, and that has profound implications in terms of the ability for these companies to innovate.

**Edith:** Now would be a great time for our guests to introduce themselves.

**Paul Biggar:** Let’s start there.

**Scott:** This is Scott Raney. I’m a partner with Redpoint Ventures. Fire away.

**Paul:** Okay, so a company comes to you for funding, and they release once a month. What do you think?

**Scott:** I don’t know that I would draw any conclusions based on they release once a month. I think in the end, I think what’s really important is that they’re doing what they feel is right for them, and their ability to move quickly enough. It would be unusual today to have a company that’s releasing once a month. I mean we’re obviously seeing for the most part companies that are releasing far more often than that.

I don’t know, I wouldn’t necessarily draw any conclusions, because I would assume that these guys know the right pace for them for whatever reason. Obviously, one of the things that we see a lot is companies that are really being driven more and more by mobile and that has real issues and challenges associated with the ability to move quickly there and some of the things that companies like LaunchDarkly are trying to help address.

I think the most important thing is we feel like it’s a company that is set up to move as quickly as required to actually be able to drive the kind of innovation we like to see and we want to believe that they are an organization that’s operating and building a software architecture and development pipeline that will be an asset as opposed to a liability.

**Edith:** I think that’s a really good point you made. So, I talked to other day to somebody who said, I asked how often they released, and they said, “Three times a year.” My jaw kind of dropped, I’m like, “Do you want to release faster?” and they’re like, “No.” I’m like that’s fine. I think if that’s a pace that you and your customers are happy with, that’s fine. I think it’s the people who want to release faster, but can’t.

**Scott:** It’s also like if you’re releasing enterprise software that’s being delivered and sitting on people’s servers behind their firewall, then the release cycles need to be more slowly, because it has to happen in a way that the customers can actually absorb it. But, obviously, more and more stuff is being delivered through those as-a-service and we would expect that release cycles would be much faster.

**Paul:** So, I think even for enterprise software. When I look at why people deliver continuously, it really started as developers just want to get there code out into the world . So I can see if you’re releasing every quarter or three times a year, whatever, developers get pissed off, but it’ll be fine.

Where I’m seeing the majority of the impetus for continuous delivery is in customer validation and in being able to get the feedback cycles of things. So, if someone is shipping once a quarter, what is their feedback cycle like?

**Scott:** It depends ultimately too on just what’s being released as a part of these releases. I mean, how much new capabilities and new functionality is being introduced? You can release every day, but if it’s something that’s like, you’re changing the color on one page that’s very deep down in the bottom of some service, who really cares, right? So I think it comes back that, yeah, maybe the way to think about this isn’t how often you release, but how significant these releases are, how much you’re actually changing and evolving the product and at what cadence is that happening?

One thing I would say is that what we’re seeing particularly for companies that have software behind the firewall, one of the trends that we’ve seen the last couple years is actually cloud-managed software. It actually looks a lot like SaaS, there’s one code base. When there’s a release, it’s pushed out, and it’s pushed out to all behind the firewall to these organizations and there’s a cloud layer that does all the management which again, facilitates allowing companies to innovate and release software much faster than they ever have been before.

That’s a bit of a side not, but I think it kind of reinforces one of the reasons that people are doing that is because they want a faster customer feedback cycle, but they also want to reduce the cost for organizations to own that software. And a lot of times that relates back to, if there’s a new release, the whole process they had to go through to deploy it…

**Paul:** We used to have this thing where you’d build software and then you’d branch off the software and you take that to release while development continues on the main branch and then you’d end up backporting these fixes for the key customers that were on those releases.

CircleCI now makes on-prem software and we ship it to customers, but customers stay on a more or less, there is one version of the software. There’s no way that we’re backporting fixes to any of the old changes at all.

**Scott:** No, and I was very surprised when we first saw this trend emerging with a set of companies that were thinking about delivering software that way. I wasn’t sure exactly how enterprises would react to it, but we’ve got three or four portfolio companies and they get no push-back and in fact, actually, I think now it’s an asset, because they can say the total cost of owning the software is substantially less than it would be if we were handing you software and you were deploying it yourself.

**Edith:** Wait, wait, wait, so, you’re saying if they’re running it as a SaaS or if they’re running it…

**Scott:** Cloud-managed SaaS, so it’s like software that’s running on your hardware. You’re my customer, you can run it on your hardware, but you don’t manage it, I do, for you. And I think that that’s a really interesting a trend, because it allows us to kind of, sometimes there are certain customers or certain capabilities where customers don’t want to move that information or the data, or that workflow, or that process to the cloud, but we can still deliver, we can still innovate and move just as quickly and efficiently as we can if we were a pure SaaS business as a vendor.

**Paul:** It’s a lovely model. We’ve got a handful of customers that are on that particular model versus the pure on-prem and for us we’re doing auto scaling of very, very large fleets and it’s difficult to do that sort of auto scaling in a pure hands off environment. So, if we sell Circle on-prem and you have tens of thousands of machines that you want in this fleet, you’re going to end up doing some sort of management.

So, the customers that fit that profile are, and I’d say this is still early stages, but, like, we’re managing their fleet that they pay for that’s on their hardware. And it’s just an easier model for them and for us as well, because we don’t have to build this perfect software fleet management, scalability management which is a very difficult challenge. We have a little bit of flexibility like we do in the cloud service where there’s an ops team that actually keeps an eye on that sort of thing.

**Edith:** So, how do you price that? Do you price in the cost of your ops team managing these instances? Is this really turning into ops as a service?

**Paul:** I don’t think it’s quite ops as a service, but it’s certainly leveraging the tools that we’ve built to manage the .com which I would describe as more, it’s not quite hands-on, but it’s sort of like, human-guided rather than just a pure software solution.

**Scott:** I think it’s only slightly more expensive to support these customers than it is a cloud customer when you get right down to it, if you do it right and you build it right.

**Paul:** And in the end of the day, there are set margins that you have to get, so, we will price it so that we get the margins that we’re looking for and it doesn’t matter what exact way that goes.

**Edith:** I mean, I like the idea, something that we’re investigating at LaunchDarkly also.

**Scott:** Yeah, and there’s companies like Gravitational, Replicated and others that are helping take traditional SaaS businesses to help get them behind the firewall. I’m really excited to see where those things go, because the reality is that building that management layer, I think a lot of times, people try to tack it on later and it’s really really hard to do that, you kind of have to think about it from the beginning.

**Paul:** I was looking at the Replicated site today and they have at the very start of their features it’s that they allow continuously deliver or they allow software to be continuously delivered to their on-prem customers.

**Scott:** And it should match exactly what your traditional flow is for whatever their customers, whatever it looks like for their SaaS capabilities. I don’t know, we’ll see what happens, but that’s a new and interesting model.

**Paul:** So, you see a lot of those kind of enterprise pitches and people. What percentage of your companies get any sort of push-back from more traditional enterprises?

**Scott:** What kind of push-back do you mean?

**Paul:** That continuous delivery doesn’t work or we want a longer release cycle and maintained branches, all that sort of jazz.

**Scott:** You know, honestly, I’m not on the front lines to having these conversations, but I’d say that that is increasingly by-far the exception versus the rule. I think that it depends on how it’s packaged. It depends on what it is.

If it’s a storage software subsystem, that’s very different, right? There are considerations that go into thinking about release cycles there and all that’s up to testing we have to do, that’s more sophisticated. But, even with that, we have a startup that’s actually doing cloud-managed storage, so I think that even that’s evolving.

**Paul:** I can’t imagine shipping a box that has software on it, like, it just seems like such a challenge to keep that innovating.

**Scott:** Yeah, yeah, I mean, I think it is, and that’s why, frankly, even in the storage space now, they’re almost all software businesses.

**Paul:** So, you talked about mobile, that’s still the interesting challenge that people have.

**Edith:** I think it’s gotten a lot easier.

**Paul:** Do tell.

**Edith:** Like, it used to be the average and this is the average App Store review was nine days and if that’s the average, that means there’s some much longer. I think Apple realized that this was really hurting them and now the average App Store review is about a day and a half.

**Scott:** Yeah, and they just announced, I just read somewhere where I think now it’s almost a two to three day commitment. But, still, two to three days is two to three days. It’s better than it used to be, but it’s still not what we think of as kind of, traditional web cycles.

**Paul:** I think the important part of this is that there has already been a decoupling of software landing from feature being turned on. So, obviously looking in Edith’s direction here.

**Edith:** Are you? Tell me more.

**Paul:** So, feature flags are this thing that-

**Edith:** Thanks for wearing your LaunchDarkly shirt today by the way.

**Paul:** So, it kind of doesn’t matter that much anymore. If you’re shipping software every two to three days for your mobile device and you have feature flags behind it, you essentially have continuous delivery, because by the time you turn on the feature for hundreds of thousands of people, you’ve been gradually spinning that up over a couple of weeks.

**Scott:** The other needed support is the auto updating that’s happening on the mobile devices now too. It used to be that you release these things and you might get it every two to three days, but your end users aren’t updating at all. And now that’s less and less of an issue as well.

**Edith:** That was the bane of our existence at TripIt, like, people on really, really, really old versions.

**Paul:** Did you stop them working?

**Edith:** Oh, I mean, the thing is consumers are consumers and if they’re version isn’t working and say they’re on a business trip to Brazil,

**Paul:** You can’t just auto-update over there.

**Edith:** They’re just pissed off at us that something isn’t working and it’s hard to get an update because you’re traveling. So, auto-update helps because then you can do it auto and not at the point of pain which for a travel app was usually when you were out of the country and already in pain and in a hurry.

**Paul:** I’m surprised there was every an option to manually update, like, what was the point there?

**Edith:** Well, I think people are so burned by the whole Windows 10 update that’s going on right now where Windows 10 has this massive update that is killing a lot of people’s computers.

**Paul:** Oh, wow.

**Scott:** I think it’s an artifact of the decisions that were made back in 2007, 2008, which is you didn’t want people to burn through their data plans. You have to realize that there’s a responsibility you have and that the end user is actually paying for all the data that’s being consumed, but that’s obviously become less of an issue now as data rates have gone up.

**Paul:** I’ve always seen that this idea of, you know, you really want to have control over your software and on the one hand you can look at it as like a free software foundation view of the world where you want to have control over everything that runs on your device. Still, you hear people who just like, I want to know what version is installed, I care about what updates are installed and frankly, I don’t understand any of it, I want to see none of that.

**Edith:** I think some of it comes from a place of fear. Like, if, you remember when stuff broke all the time, I just want a stable version and that’s why people want to know. If you have trust then you don’t really care.

**Scott:** I agree with that.

**Edith:** Like for a website, like what time, do you ever look at like a SaaS product and ask what version it’s on? No.

**Paul:** Right.

**Edith:** But why do you agree?

**Scott:**


<blockquote>I think things used to break, I mean honestly, and now they don’t. I think part of it is that we’ve gotten a lot better as an industry at doing all these things.</blockquote>


**Paul:** It’s almost like there’s a correlation between continuous delivery and thing’s not breaking as much.

**Scott:** There might be, there may be there’s that relationship. You guys gotta do a podcast about it.

**Edith:** And we’ve got to have a guest named Scott. No,


<blockquote>I think that things still break, it’s just that it’s much easier to fix them now.</blockquote>


An example you were just giving of having a physical box somewhere, if something broke you would have to go physically update that. I saw this great talk in, it was like Continuous Lifecycle London, it was this lady who used to physically solder programs into cash registers. So I mean if there was a bug.

**Scott:** Okay, that is exact opposite of what we’re talking about here today, right?

**Edith:** Yeah.

**Paul:** So like money things, is that what you mean?

**Edith:** Like a cash register has programs in them, and to update the program you would physically take a chip and solder in the new program.

**Paul:** So I thought we were talking about like parts of the CPU, there’s the cache, there’s the register

**Edith:** Oh no. This is literally cash, C, A, S, H.

**Paul:** Good clarification. – Yeah. Okay sorry, listeners at home were wondering which it was.

**Edith:** But I think a lot of, that was the original software.

**Paul:** Right, yeah.

**Edith:** You know, it was just one step up from the physical hardware, and so there’s a lot of legacy of, oh it needs to be perfect because it’s gonna get placed everywhere.

**Scott:** But I tell ya, you know what’s interesting is just how quickly I think big enterprises are changing the way they look at that. And I actually think that it bodes really well for you know the startup ecosystem and for innovation, and that there’s an increasing amount of trust. And you know, I think that’s a phenomenal thing and a great catalyst for all of us here.

**Edith:** Do you have any stories of enterprises or anything you can share?

**Scott:** I don’t know that I have any specific stories other than I can just tell you, as I said, anecdotally in our businesses that are going to enterprises, the way that they do release processes now has you know, has changed.

**Paul:** Well when did you see that tipping point?

**Scott:**


<blockquote>I would say probably two to three years ago is when it started happening, and maybe one to two years ago this idea of cloud managed software became more widely accepted.</blockquote>


I also think Amazon AWS, has been a big part of this, which is actually just this idea that, it’s obviously very different, but the idea of relying on a third party for some kind of element of cloud managed software and infrastructure has kind of changed the way that people think about, you know, expectations.

**Edith:** It’s made things a lot cheaper and easier.

**Scott:** Yeah, it’s that for sure, and it’s also just like you know, what used to be that we had to run our own hardware and now we can turn all that infrastructure over to somebody. So hey, you know what, it’s not that big of a deal if somebody wants to update. If we can do that, then if somebody wants to update software on the fly for us, they can do that. You know?

**Paul:** There’s an interesting parallel to [Jeff Bezos’s last annual report or letter or something](https://www.sec.gov/Archives/edgar/data/1018724/000119312516530910/d168744dex991.htm), he talked about the difference between type two decisions and type one decisions. That type one, I can never remember which is one and two but. Let’s call ‘one’ the one that is very, very difficult to change, and you have to put an awful lot of forethought and planning into it. And type ‘two’ is the decision that’s very easy to change.

**Scott:** But do we spend the same amount of time on type twos as we do type ones a lot of times? Even though one is easier to unwind, right?

**Paul:** Yeah, and so I think where you get this thing of trust, you know, it ties a lot to type two decisions. And the same thing with like a box that you ship into data centers is a type one decision. Or a soldering into a cash register.

**Scott:** M aybe that’s one of the reasons why. I mean


<blockquote>The ability to unwind a bad release, we’re much better at that than we ever were before</blockquote>


and part of it is through all the stuff we’re talking about here, right?

**Edith:** Yeah I mean reversibility, I hate plugging my own company so usually I let Paul do it. Feature flags are really about reversibility, the fact that you can always roll back very quickly to a known good version without having to redeploy.

**Scott:** Right.

**Edith:** It creates a lot of freedom.

**Scott:** Yeah so hey, you know what, maybe it wasn’t perfect while the reality is the cost is low, because we can get it back to where it was before.

**Paul:** There was a blog post I wrote several years ago back the Amazon Kindle on iOS disaster. So Kindle released a new version on iOS that deleted all their customers libraries.

**Edith:** Well Apple does that on purpose now. They do! It’s a feature, not a bug.

**Paul:** I mean it deleted their cloud libraries, not just the music that they had on their phones. What happened was Apple fast tracked Amazon’s new version of Kindle, and you know a day later the disaster had been kind of largely averted. But it was a disaster I feel that happened in the first place because of the lack of continuous delivery.

That they have to ship this big release, they probably shipped it every month or something like that and the confluence of several different decisions have to be made at the same time, and so there’s a big kind of like type one, are we gonna ship this decision because there is no type two, let’s immediately and very quickly roll it back and the result to that is a whole bunch of software that goes there together that has unintended consequences.

**Scott:** The N squared problem with all those features like you know, how does it work? Yep.

**Edith:** Yeah, but we were talking before about the air force jet disaster, I like Scott’s description of it.

**Scott:** Well I don’t know, yeah I don’t remember exactly what part of the description you liked, but I mean it’s just interesting to me that this is a you know, 10 to 15, 20 year project that’s gone on and the scale and scope of it, it’s basically just something that was, it’s just trying to be a little bit of everything to everybody and as a result it’s not really good at anything that it does.

When you do 20 year release cycles, that’s what happens. You spend you know, a trillion dollars on something that in the end is not nearly as good as maybe even its predecessors of many of the capabilities that they were looking for. I would love to believe that there’s the concept of continuous delivery and deployment that would be possible for you know, projects of that scale but you know, I don’t know.

**Paul:** I mean it sounds almost like ensilage, I don’t want to suggest that this might actually be the case, but it sounds like it might not actually be in people’s interest to you know, deliver a working product versus continually pumping money into the–

**Scott:** Well that’s, that’s–

**Paul:** And I wouldn’t like to suggest it’s any sort of political or lobbyist motivation behind this thing at all.

**Edith:** So I grew up in DC, I’ll briefly defend DC. I do think people wanna see successes. I mean like healthcare.gov was an awful, awful, awful egg in the face for involved, nobody came out looking good. And it wasn’t like oh you screwed up, here’s more money to fix it. You know, they brought in a completely new team and started over again with very much continuous delivery processes.

**Paul:** Well that was a sort of a difference in how previous plans had gone. So normally when that thing happens you just keep money pumping into it until someone gives up, and then the same team gets deployed to a different part of the government to get hundreds of millions of damage.

**Edith:** Yeah, I think the sad thing, it was so the extent of the jet thing is that they can’t even take off. It’s not like they have a sporadic glitch that might affect them. It’s that like like literally these are you know, a trillion dollar paper weight.

**Paul:** One the kind of comparisons that people always make is real engineering products to software engineering, or processes, and you start to see in the real world a little bit more of continuous delivery like creeping in. So you look at the hardware startups in Shenzhen for example that are changing the cycle time from, you might get a prototype in a week here if you’re lucky, and if you’re in a different part of the world you might get in a month. In Shenzhen you get it in a day.

You’re missing a component, you go down to the component market and it’s a multiblock warehouse that sells you the exact component you need and you can get that cycle time down really, really low.

**Scott:** It’s also that so many of the, you know, we look at a lot of hardware projects too, and so much of it now is being done in software. So what you really look for is almost like this generic hardware platform that allows you to build the software, build software capabilities so it’s that you know, if you do make mistakes, or there are issues, or there are antenna problems, et cetera, hopefully many of those things can be fixed in software. Sometimes that’s just not possible.

**Edith:** Have you ever seen a company just go completely awry with an Air Force type disaster?

**Scott:** I have. I’m not gonna, I won’t mention names. I haven’t seen it in a long time, honestly. In terms of like just that I’ve seen people, I’ve seen companies do that where it’s not the software or the product, as much as it is maybe the way they thought about building the business.

One of the things that’s happened along with continuous delivery in software is actually much more nimble go to markets that are being built around businesses that allow you to solicit feedback much more readily and actually do–

**Paul:** Validate them earlier.

**Scott:** Yeah, be able to validate them earlier. But also like it’s not the top down you know, long sale cycle that there’s more bottoms up that allows you to get feedback and then tune you go to market which obviously then rolls back into your product, and you know


<blockquote>it’s a virtuous cycle where the continuous delivery capabilities actually allow you to evolve your business model too.</blockquote>


But you know, so it’s rare that we see companies just kind of fly right off the end of the runway or right into the cliff in the way they used to, but it still happens from time to time.

**Paul:** I see a bunch of it. So I talk to very, very early stage startups that are, you know their question is how do we raise money sometimes. Or you know, we’re running off our savings. And for a lot of them that have done and a lot of times my answer is, you know you don’t have product market fit, you need to validate and iterate your way there.

I see people who are you know, running off whatever meager savings they have because they never learned the lessons of the lean startup, of continuous iteration, of validation. But I think that that’s mostly hopefully kinda taken care of by the time they hit any sort of traction or product market fit. Like they don’t get that far, they don’t get to like.

**Scott:** Yeah it’s rare, typically a lot of that is the very initial product market fit, the reality is product market fit isn’t a, it’s not a one, there’s not, it doesn’t happen all at one time, it happens over a period of time.

**Paul:**


<blockquote>It’s never the early vision that’s ‘it ‘</blockquote>


so you have to be good at iterating to get there.

**Edith:** Well the market itself changes.

**Paul:** Well yeah.

**Edith:** Like things like if you try to build an app 10 years ago, like people were trying to build app 10 years ago, it’s just the carriers made it impossible to put them on.

**Scott:** Absolutely. We funded a number of businesses that did that, and not easy companies to build.

**Edith:** Yeah.

**Paul:** I guess you’re kind of in the business of funding a lot of people who are ready for something that hasn’t quite happened yet.

**Scott:** Yeah.

**Paul:** And so if you don’t know, and correct me if I’m wrong here but if you don’t know exactly how or when the thing that they rely on is going to happen, so they need to be constantly iterating, constantly validating to get that right.

**Scott:** Yeah, I mean and sometimes, unfortunately, the market, they’re just too far ahead of the market. Which is you know, there’s no amount of iteration and amount nimbleness is gonna help you in that situation if customers just aren’t ready to for whatever reason kind of embrace the value proposition you’re putting forward.

**Paul:** It’s very interesting, around the start of, of CircleCI, so there were companies that were like two years ahead of us that died. Or in one case that pivoted to a different product. And then companies that started about a year after us, it was too late, the market was kind of, the opportunity was closed.

**Scott:** Yeah.

**Paul:** And so like the too early, too late, there was one sweet spot, and it’s not like we knew it. We knew why in retrospect, we can look back and we can say it was the tools and it was the freedom of allowing your source code to escape that made that the thing, but you can’t tell at all.

**Edith:** Yeah, I love to hear some real examples from Scott if you can say anything without breaching confidentiality.

**Scott:** About?

**Edith:** Companies that were too soon, too late.

**Scott:** I’m always terrible about bringing up, to drum up things in real time.

**Edith:** Or just advice you’d give because you’re a board member.

**Scott:** Yeah wouldn’t wanna, I always wanna be respectful of folks, because the reality is, one thing I can tell you about this timing thing, it’s more often being lucky than good, sometimes being really good allows you to time it right because you really understand all the things coming together. A lot of times, you just timed it, you just got lucky that you timed it really, really well. You know the thing that, the feedback that we give all the time though now, and this is very different than it was even like five, six, seven, eight years ago is that


<blockquote>you can get so much more feedback on product and product market fit earlier with less money than ever before and you’re crazy not to do it.</blockquote>


And so the definition of minimal viable product at which point you can go out and actually start collecting this feedback is always the hard thing, it’s like where’s that line. Like what is acceptable, and what isn’t acceptable, what’s enough and what isn’t? You know, that’s an inexact science and sometimes you know companies will make mistakes about not putting in enough or taking too much time.

We spend a lot of time sitting around board meetings talking about how can you go out and you get the product in front of folks and start to solicit real feedback. Even at the expense of thinking about revenue. So you know I think that once you’ve raised a little bit of venture money, you kind of have the luxury of actually being a little bit more, thinking a little bit more long term. And it gives you the ability to spend time thinking about, for instance like any developer facing business, you know our feedback is always **get developers to love it**. Win over the hearts and minds of developers, and then worry about monetization later, right? And with a little bit of venture money it’s easier for a company do it.

It’s frankly easy for me as a venture guy to tell entrepreneurs to do that, and it’s sometimes a very harrowing experience, but you know what you want more than anything is to get a bunch of people using your product, and loving it. More often than not, if they really love it, and they’re using it and engaged in it in a really meaningful way, there’s a business model to be layered on top of it.

That’s not a great model for all companies, but certainly for ones that, you know the ones that I spend a lot of time on that are selling through developers to other people and organizations, the most important thing we can do is just build something that folks love. The other thing that I would say is, one really interesting dilemma then is, we’ve talked about this before, but these companies that actually used developers and you know, because through continuous delivery developers are playing a bigger and bigger role in selecting the components of the infrastructure that’s actually used to build, not only the product, but also that the businesses run on.

What you wanna do is you wanna win over the hearts and minds of developers getting to use it, but at some point you have to trigger in your business the ability to actually market to the people that ultimately will be paying for the product. And how do you simultaneously run a marketing campaign organization that’s winning over the hearts and minds of developers while convincing product managers or CFOs that they should be paying for product that has kind of made its way into the stack through the developers. That’s a really challenging exercise to go through so.

**Paul:** Github had this concept that they call the clamp, that’s coming from the bottom and coming from the top at the same time.

**Scott:** Yeah.

**Paul:** So when you’re company that’s like GitHub, and I mean this is several years old, but even by then they were, they were huge and they were able to go for the top down CIO sale at the same time as they were doing the bottom up. But I think if you’re a much smaller company that there’s much more of a challenge getting that.

**Scott:** Yeah, and I would argue by the time they started executing on the clamp that they had won over the developers.

**Paul:** Oh yeah, all of it.

**Scott:** Again that’s kind of actually saying once you win over those folks and the amount of leverage you have in this conversation is very, very different. And so I don’t think the right way is to think about coming from the top, and then eventually kind of try to build up the bottom. And you know, that’s an obvious statement, but frankly it’s amazing in the heat of war how many times companies make mistakes on that.

**Edith:** Like you mean, are you always in favor of going bottoms up then?

**Scott:** I’m not always, it depends on the business, and obviously what I’m talking about a lot of here is kind of these developer facing businesses, but and so there’s certain cases where that doesn’t make sense, again like some core enterprise infrastructure businesses, you know that’s not a bottoms up game.

I do think for, and in a lot of SaaS businesses it’s not gonna be a bottoms up, but I do think that any time where you’re building something that’s kind of democratizing some capability, in some ways the best thing to do is to get as many people you can as possible, and then you’ll find that it’s much easier to monetize.

But it requires generally for these companies to hire on some different capability, the ability to kind of exert that pressure from the top. You know, sometimes that’s an unnatural act, because you’re dealing with folks that are building these products as developers building for developers.

**Edith:** Certainly I see both sides, at TripIt we were hugely successful because we had all the individual travelers, and then travelers also have budget, because by their very nature they’re usually almost always somebody’s traveling because they’re important.

**Scott:** Yeah, exactly.

**Paul:** So you spoke on, was it Tom’s podcast a while back?

**Scott:** Yeah.

**Paul:** I was listening to that, and it was great. And if you listen to this, you should go back and listen to Scott being on the Tom’s Podcast.

**Edith:** That’s why I wanted to have him on ours because I was like, wow, I would love to just talk dev tools for a while.

**Paul:** So one of the things that I thought was really interesting was so you separated the developer tool ecosystem to like four bits, and one of them was API’s around existing products. It seemed really interesting to me that you know, we’re talking about bottom up versus top down.

When you think about the mechanism by which you know, software takes over the world or software eats the world, whatever it is, that it’s those companies that do exactly the same thing but have an API on it that is sort of the front line of those like transition from the older companies to new companies and being disrupted just by having an API that the developer picks. And so by the time that they, I think you said this, by the time there’s a decision to be made, it’s already been made.

**Scott:** Yeah, and typically those are commodity capabilities and features, so you know, Twilio and Stripe and other things like this, the reality is not commodity in the sense that it’s not really hard to do because it’s very hard to deliver those capabilities, but more often than not you’re not gonna win or lose based on your ability to better execute integrating voice or text into it than the next guy.

What you don’t wanna do is spend your valuable engineering and developer resources recreating something that in the end probably won’t allow you to win in whatever segment you’re in, but are absolutely important essential parts of the overall experience. And when you can find those things, and it also helps when you find those things that actually have natural business models attached to them you know where it’s well understood that you pay for the consumption of those capabilities. You can build an extraordinarily powerful businesses so.

**Paul:** I love the background checking as an API. It’s just such a good model. Like exactly as you say, like you’re used to paying for background checks. It’s not core to your business.

**Scott:** Yeah, and it’s not like one company’s gonna be better at background checking, and that’s gonna allow you to differentiate, and you know–

**Paul:** Lyft isn’t gonna beat Uber by flexing its background checking muscle.

**Edith:** Well. ..

**Paul:** Well maybe, maybe.

**Scott:** You gotta be good at it, I mean the bottom line is you gotta be really, really good at it, but it’s typically not the basis of competition.

**Edith:** Yeah it’s table stakes.

**Scott:** Yeah. We love finding those types of companies, the reality is they’re not as plentiful, there’s a lot out there, but it’s hard sometimes to find the ones that have the big scalable business models attached to them.

If you ask me, getting going into the future, I mean you kind of look at the typical application that’s been built, how much of it will come from API services like that versus stuff that’s built custom for that application. I say increasingly there will be more and more that will be delivered through these API services, and you know these.

**Paul:** And they’re all consumed bottom up?

**Scott:** Well I think in the end that is the best path to success because you’re not gonna convince developers, typically it’s hard to convince developers to do something, they have to you know, kind of want to do it themselves.

I also think that what ends up happening is somebody’s tasked with the you know, you need to build this capability, and they’re like “why should I? that just seems crazy that I… there’s gotta be some way I can just find an API to do that.”


<blockquote>Which is really cool, that’s the default question that a developer asks, is there an API that can do this for me?</blockquote>


**Edith:** Well do you think it’s kind of an outflow of the whole stack overflow thing where it’s like, I’ll just Google that.

**Scott:** I think it’s like and it’s like the whole thing that’s driving I think microservices to a certain extent it’s like look, people wanna be, they wanna like focus in on the stuff that really matters to them and their company.

**Edith:** Yeah.

**Paul:** Right. I think there’s a natural analogy between a microservice and a third party company that is providing it.

**Edith:** Yeah, I definitely see that, I mean that’s why people are coming to my and Paul’s company, is they’re like well we know we need this. We don’t wanna build it.

**Scott:** No, yeah, and the reality is you’ll build it far better than they would. Anyone that goes out and tries to do what Twilio is doing right now, I mean good luck. Good luck, they’ve got you know, several hundred engineers building capabilities to deliver a really compelling set of services that are global in nature, that are route optimized. I mean it’s like, good luck trying to recreate that. But it’s not threatening in any way to kind of absorb that into your capability.

**Edith:** There is an interesting counter swing where like Dropbox just moved everything in house, you know, so I mean what’s your take on that as a competitive advantage?

**Scott:** In terms of the infrastructure?

**Edith:** Yeah.

**Scott:** I think you get to a point where in many cases I mean, this is a different conversation, but we’ve heard this again and again, but I do think that if you’re an organization that has kind of predictable loads and you’re not optimizing for peak capacity through when you run the numbers, it can be cheaper to run you an infrastructure.

As a guy that loves the cloud, it’s like you know, it’s like I say this with a great deal of humility, but you know, there are a number of companies, we’ve seen a bunch of companies who come in, and they pitch to us, and they’re negative gross margins, but they say we’re gonna move off of Amazon and bring it in house.

We’ve seen two or three companies that have done it that have gone from negative gross margins to sixty, seventy percent margins in the span of months. But it really, I think that makes sense for a subset of companies out there with a particular workload. Either they’re very IO intensive, or they’re not, they’re highly predictable, you know, where you can capacity plan, and you can drive high levels of utilization.

**Edith:** Yeah, I think you put it really well, it’s just what are you outsourcing, what are you insourcing? Like here at Heavybit we’ve outsourced our office.

**Scott:** Yeah.

**Edith:** And it eventually–

**Scott:** It’s a nice one too.

**Edith:** Yes.

**Scott:** Try replicating this one on your own.

**Paul:** So when you’re looking at people who say oh we’re gonna bring this on-prem, how do you know the difference between someone who has no idea what they’re talking about and someone who’s actually going to do this?

**Scott:** Meaning that they’re making the right business decisions or meaning that they are capable of bringing it in house and running it as efficiently as they need to?

**Edith:** I guess a bit of both. I mean like how do they know that when they get there their margins will be, will be what they expect them to be?

**Scott:** Yeah it’s actually, you know, I’ve gone through this a couple times, I’ve gone through this exercise, we walk through it, and it typically, when you sit down and they kind of walk through the numbers, it’s actually not that complicated of a spreadsheet, it becomes obvious.

**Paul:** Right, right, right.

**Scott:** I described some of the characteristics that might drive people to make that decision. You know, sometimes the bigger question is are they gonna be, like okay so, you have baked into that a set of assumptions on just how efficient you can be at running that infrastructure. Will you be able to be that efficient at running that infrastructure? Are you good enough, do you have a good enough operations team to do that? And obviously that’s a big part of the assessment we would do as a part of a diligence process.

**Edith:** Yeah.

**Paul:** We did the same thing, it was literally a spreadsheet and we got it down to what is the cost of a CPU hour, and what is our intuition around the cost of a CPU hour can be.

**Scott:** Yeah, you know and the thing that you wanna be careful about when you do this is that you’re again, you’re not undermining all the operational flexibility that’s introduced by continuous delivery, right? Okay, now we brought it in house, but man, you know, when we want to launch a new capability, a new feature, or a new whatever, now we’re stuck in that old process of where we’re gonna bring in some hardware and we gotta you know deploy that and scale that.

Are you undermining your ability to move quickly? And this is something that you know, that’s a conversation you have to have with folks and make sure that they’re building the capabilities so that modern capabilities for a software deployment to ensure that they can do that hyper efficiently so.

**Paul:** When we launched our CI for OSX we moved from you know, our CI for Linux runs on Amazon, so we want a new machine that’s an API call. We moved it into, you know we want a new machine, that’s an email and a couple of days and an invoice that needs to be signed.

The difference between you know, the speed at which we’re able to get new capacity, the OSX thing sat in Beta for quite a long time, because we just constantly added new machines all the time for the new customers that were coming in. It grew so quickly that we never, we were never anywhere near hitting that capacity, and so we were, I think we were in Beta for a year on that as a result.

Once we kind of got it to like the level where it didn’t take a human on our end, it got to be a lot faster that we could provision, but it’s still never, you know it’s never going to be the Amazon speed.

**Scott:** I think the thing that you know, the decision, when you make this decision, if you’re gonna move off of Amazon and run it on your own infrastructure, it needs to be something that you have to do based on economics as opposed to something that you want to do.

Like you know a lot of these companies, if you trying to squeak an extra five to 10 percent of gross margin out, you know that’s on the edge of maybe it’s worthwhile, but probably only when you’re really significant in size and that five to 10 percent really, really matters. You know, a lot of the companies we see doing it are doing it because their business model’s upside down.

**Paul:** Right.

**Edith:** Yeah.

**Scott:** Because I think that the flexibility from Amazon capabilities, all that stuff, when you can focus on the things that really matter, you can invest your resources, you know, in places where it’ll drive long term differentiation, and that’s what we’d rather see our company spend their time.

**Edith:** Yeah, that’s a good way to put it. It’s something that you do when you’re mature and trying to eek out margin, rather than when you’re trying to innovate and grow very quickly.

**Scott:** Yeah, except there are cases, even in the early stages, based on the nature of their workloads where they, you kind of have to. But that’s I think the rare exception as opposed to the rule.

**Edith:** Well it’s optimization rather than growth.

**Scott:** Yeah.

**Edith:** Yeah our advisor Sean Byrnes was at Flurry.

**Scott:** Yeah.

**Edith:** And he always laughs, he’s like, you’re gonna build your own data center some day.

**Scott:** Yeah, you know, that’s something we should all aspire to with all our companies. At some point to be big enough for we wanna build our own data centers.

**Edith:** So he’s like not right now, but in a couple of years you’re gonna come to be for advice. I’m like, I know.

**Scott:** Then we gotta to the big CIO’s of the Fortune 500 companies and they’re trying to figure out how to get out of their data center. So the real answer is somewhere in the middle I’m sure.

**Paul:** Maybe they can sell them to Dropbox.

**Scott:** Yeah, exactly.

**Edith:** Hopefully I can sublease their data centers for very cheap. Well we’re almost out of time, but we loved having you as a guest. Do you have any final thoughts?

**Scott:** No, no, thanks for having me, I appreciate it, it’s been a lot of fun.

**Paul:** Oh thank you.


