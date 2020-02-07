---
author: Kimh
comments: false
date: 2018-09-17 23:16:36+00:00
layout: post
link: https://launchdarkly.com/blog/the-benefits-of-using-monitoring-gateways-architecture-for-large-scale-it-environments/
slug: the-benefits-of-using-monitoring-gateways-architecture-for-large-scale-it-environments
title: The Benefits of Using “Monitoring Gateways" Architecture for Large-Scale IT
  Environments
wordpress_id: 193361
categories:
- DevOps
tags:
- monitoring gateways
- monitoring infrastructure
- test in production
- waze
---















In July at our monthly Meetup, we focused on testing in production with systems and processes at scale. Daniel Mor, Systems Operations Engineer at Waze, gave a talk about monitoring infrastructure.


<blockquote>“You need to think about solutions to monitoring issues as not as small things, [but]…as a framework. If a developer asks me to monitor something, after that another developer will come and another developer…and most of the time the things will be the same. So I build in a framework point of view.”</blockquote>


Watch his talk below to learn more about how his small team manages real-time infrastructure based on a miscroservice architecture that receives high volumes of traffic. If you're interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).
































[embed]https://youtu.be/trrBhylMbC4[/embed]

TRANSCRIPT

Basically, I just want to thank um...the three gentleman's before me, and like if we were closing the loop, you know there are experiments that we heard about you know in the Facebook slideshow. There is the Kayenta solution which is amazing and by the way, Waze is a user of the Kayenta solution and maybe I will talk about it later on but both from the upstream and the downstream everything relates to metrics, numbers and monitoring, okay? So I think that it was...it was unplanned but I think it would be a great way to you know...like finish today's session before the Q&A and talk a little about monitoring, okay?

Now as I mentioned before about this slideshow, this slideshow is not about a specific solution, okay? It's about like way of thinking when you take large-scale data centers, information, like data centers whatever. And what you need to take into account is we see it from our experience eh...eh in order to you know bypass the obstacles and they will come.

Okay. So my name is Daniel. Nice to meet you, Daniel Mor. I'm working at Waze, for Waze. So basically I'm part...I'm located in Israel most of Waze headquarters, engineering, whatever, most of the team is located in Israel. Um start off, it was bought by Google a few years ago of course. I'm part of the infrastructure team what we call the IFS team, in Google terms its like a SOE if you're familiar in the complete word in what call DevOps okay where mainly they are the means of the production team, the production and solution of Waze and we are also the ones to get...you know at night, when something is not working, two little kids, wife, after dinner want to sleep, pager, okay? This is how I look like when I get a pager so (audience laughs) so hopefully, it will not happen now.

Basically, some more details about our team because it's very relevant to monitoring and the complex situation that we could have but we are trying to make it very convenient. So as mentioned we are part of Google, we are like autonomous squad inside Google. Maybe the most interesting thing to note is that we are also AWS users because back in the days Waze was based on Amazon, we're in the process to migrate to JCP. A lot of our services is there but currently we are multi-cloud which makes monitoring even harder, including the experiments and stuff like that, okay? Um I think, I don't love to read...you know sentence from the slideshow but I think that our service has scaled up, first our attempts to scale up slower, is something we have to mention. We are a small team managing huge amount of traffic, services, incidents, etc. Our infrastructure is mostly based on Microservice architecture, okay? Uh with up-layer, cache-layer, database-layer, etc. A very very big...you know performance orientated real-time infrastructure and we need to do things right or at least try, okay trying is very good and important thing.

Okay now there is a slide where...and again it's my terms for today, this is what I call the classic way of monitoring, okay? And again as I told it's something in general, okay, not a specific solution. So how many in the audience like familiar with the eh eh you know the way of working that I am in DevOps at some nice company, maybe in the Bay Area or maybe in Israel, and I want to monitor something so I install a monitoring server, and its not relevant which solution, I install monitoring agents on the machine that usually are, you know, pre-made, pre-ready. They're basic, they give me a lot of opportunities and stuff to do and pressing the play button, right? Most of us familiar with this thing. It's great, it's amazing, it's working but when you get bigger it becomes problematic. Just one little example, when you...when you become bigger it's not just the number of machines that you need to configure with things like you know maybe Puppet, Chef, tools like that like automated tools to...to develop configuration and such.

It became also more and it's like it's...it's always happening it's like becoming more from normal monitoring to APM related monitoring. APM, Application Performance Monitoring, right? I don't really care about the single server or the single disc, I working with microservice, API's, I want to understand they...you know behave as neither and A talks to B which talks to C, I have a lot of dependencies maybe I'm working with the low latency eh...um environment and such so its become a lot more complicated.

Imagine, you know in simple terms that each new feature at Waze needs to be monitored okay? So back in the days, I need to go to all of the servers of the service and do client side configuration, it's mad! And we really believe in velocity and we need to run quick so it's not the way to go. So what we can offer or what we can plan, by the way, this is exactly what I just told you about the problems of the classic way, okay?

And I also prepared...I know that you know today technical people will be in the audience so basically the slideshow as I see it is like a tutorial that maybe you can use later on with the bullets of what to take into accommodation when I'm planning such monitoring infrastructure um...everything written here is things that you know...we we suffer back on the days from, maybe you're familiar with them, maybe not, but if there's a chance that we will save you something it's good, okay?

Okay. So as I mentioned in large-scale IT environments the per-instance, per-computers is less relevant. We are more interested in the microservice and application, okay? Of course there are different levels but basically this is it. Most traditional monitoring solutions are more like working with the classic way of monitoring. CPU, RAM, per-machine things like that, okay? In order to make it more APM related point of view I need to work out, and by the way this is the reason that there are APM solutions out there okay, specific for this needs. But I don't want to get rid of my current monitoring solution, maybe, I just want to extend it someway, okay? Um monitoring hundreds of new applications, features and such become problematic okay? And of course what's important to mention and it will occur in another slide from a different perspective, monitoring...by the way this is a...if I may, before I joined Waze I was for a lot of years freelancing, doing domain of DevOps and such.

Monitoring is not just tech, after all, you are working for a business and business you know want to earn money and such and a lot of other people, not just tech people, watching the graph and maybe analyze it and things like that so you need to remember it both because the output, you know have a lot of eyes and both...and I will get to it in a later slide, you need to consult with other team members, which are not just technical, while building the solution. And I think this is a real problem that not all of the time eh we are...used to...used to commit or to do.

Okay? So what I call the recommended large-scale way...and again just from our own experience, it's something that put like a mid-layer between if you will, the monitoring service, let's call it monitoring clients, you know the service, and the monitoring system. Okay? Because we need a monitoring system, it could be something that we wrote, it could be something that we bought, it could be open-source, everything is okay. But I think that if you're using something that called monitoring gateway and the counterpart which called monitoring endpoints on the monitored clients, your life apparently will be easy. Mostly if you will want to go, okay? And now we will deep dive into this subject.

So again, it's just an example but I think it's a good example. Imagine that we are working on a microservice setup and architecture okay? Let's imagine, just imagine that we have some Java code, microservice eh, okay? The Java application knows what he knows to do and what he needs to do. We really believe that if you will take this java application and this part of the micro-service stuck, the tools of the Java application, you will configure or code something that's called monitoring end-point. Which basically could work in which article that you prefer but HTTP is a good example and what will happen by the sense is that this Java main process will tell everything that he know or needs to tell to this monitoring end-point.

Your life will be a lot easier because then you can take all of this information from the manual on-point and based on your judgment push, pull, send it to different places which basically...the next place on the chain, instead of the monitoring system...and we will still understand why will be the monitoring gateway.

Now again, monitoring gateway is a term that I invented for this lecture, it's more understanding the concepts. Basically, I am telling you that I am taking my clients server architecture and put it on a layer, okay we can monitoring gateway inside but of the main concept of the solution is the monitoring endpoint because it's the one that closes to the application and knows all of the information from it.

So basically what is a monitoring gateway and again, this is the reason we are here today. Monitoring gateway is as I see it most of the times will be a custom made solution. As I see it, it's not something you will buy. It's something that you...big companies most of the times you know code their own monitoring solution because the market not always can cope with what we have okay? So basically its some kind of mid-layer between the clients, monitoring clients and the server. Now...it's one of the most important things for the full APM solution and why because the monitoring gateway holds all the logic, okay?

For example, if you know and I guess you know and I'm sure you know, monitoring also costs computer networking stuff like that, now there is always the...the decision if I want you know, my monitoring clients to work harder or the monitoring server to work harder. With the monitoring gateway, mostly talking with the microservice architecture, you creating...by self as a microservice which could be auto-scale, and it will take all of the responsibility for the computer and such, okay?

So for example, one of the most interesting things I can do, is metrics aggregators right? You have different services, different information, we...mostly on Google, we love raw information okay? We love...but then we need to take all of this information and do something with it. Now, I can do it in the middle layer and save all of the computers and you know waste of CPU, I mean as such, from the client that need to answer quickly, client request. Or the server, the monitoring server which is busy, okay? Even if its a cluster it will be very busy and maybe holds the fountains and things like that.

So this is one thing. Support a rich set of features, ex...another example of course as I mentioned is aggregators but you can do stuff like...you can publish API's of your monitoring gateway that people in the company could use in order to fetch data, okay? Monitoring gateway, not steal the monitoring solution on the eh end of the tunnel but you can also choose what information like a proxy from the monitoring gateway will bypass to the monitoring system, okay?

Now, when the developers need to create some dashboards and stuff, okay, which are not part of the monitoring solutions and the monitoring server on the end, it can use the API's of this monitoring gateway in order to fetch the data in case of custom, per team, per solution dashboard, okay? You know like blue eh like eh red, green, yellow whatever, for this team. I don't need the abilities of the monitoring system that maybe even doesn't have these abilities, okay?

Another thing and this is something we do specifically at Waze, we allowing our developers and maybe it's something that we will talk about in the Q&A, their ability to talk or to talk to configure this monitoring gateway. I mean if I'm a developer and I want statistics, something very complicated for microservice A with microservice B I want maybe to...you know get them together in order to get to some state of mind, I can do it on the monitoring gateway level and from there it will be automatically shipped to the monitoring solution, okay. So at mid-layer, very powerful one that could help me a lot. Okay?

One thing that I want to mention which is very very important, when you getting grow eh and getting big, when you grow and getting big, the issue of dependencies, both by microservice A to B, B to A, but both of the beckons, for example, microservice A walks it Memcache and Cassandra okay? If you are the on-call at night and you get the escalation pager you don't have time to, you know, open the book of all services and trying to understand from scratch what's happening. You want to see one dashboard okay, with all of the details. Because all of the information bypass the monitoring gateway it has all the knowledge and all the logic so you can connect between microservice and the beckon services they're using and get the full picture of the flaw, okay?

And basically, it's saying you coming back to sleep earlier okay? You save 10 minutes from your sleep. Um okay, another thing that I want to mention and by the way I did...haven't...write it but again you could start you know from being small and then become large and you know maybe you will find out that your current monitoring solution is not enough. So another thing that you could learn is that if you come back to this slide you can understand that it becomes quite...quite easy okay, to switch your monitoring system because if all of your data exists on your monitoring gateway so just need to replace the end of the tunnel with some different softer solution and the data will continue to flow so basically it's a matter of architecting, making your life easier with the look forward, okay.

So basically um, and again I don't love to read sentences but its things that you know, I wrote because I really believe them. When you are architecting a large-scale monitoring solution, think map and plan. Again, it's buzzwords but they're important, okay? If we will write with them too much it will be really really complicated to do eh...I think all of you know if you read some Essary, you know concepts and stuff in Google and that ways, we believe in this stuff from the moment we develop. Not after we got the problem, it's a huge difference, okay?

It's a state of mind. You need to make sure that everything is monitored as needed from the start. Not easy, but this is how it works in large-scale. Keeping the monitoring environment, you know aligned, synced and...healthy is not an easy task and it will require resources. It's not one time job that you know, you build infrastructure and such and hello, hello! You need to continue to work on it all the time and most of us, and of course, our managers and our budgets need to take it into account. It's decent work that will never finish. Okay? And we need to make it better, we need to try to make it better all the time.

Okay, as I told you before, remember monitoring is not that tech core. The monitoring has aspects of business okay? Of course there are tools that are using the data from the monitoring solution in order to get to these details but exactly you know as in machine learning and stuff like that, it will need always the best raw data that you can give to the solution in order to get to the right conclusion, so at least closed. Okay. Now...and this is like the last bullet. If for example, I'm a developer on the monitoring team or whatever, just so you know, you need to think about solutions to monitoring issues as not as you know eh, eh small things there, small things there, you need to think about it as a framework because if a developer will reach to me and ask me to monitor something, after that another developer will come and another developer will come and most of the time the things will be the same so I just need to build in a framework point of view and not just simple solution point of view.














