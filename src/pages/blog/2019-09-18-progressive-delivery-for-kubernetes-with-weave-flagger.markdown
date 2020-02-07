---
author: mattdel
comments: false
date: 2019-09-18 16:35:12+00:00
layout: post
link: https://launchdarkly.com/blog/progressive-delivery-for-kubernetes-with-weave-flagger/
slug: progressive-delivery-for-kubernetes-with-weave-flagger
title: Progressive Delivery for Kubernetes with Weave Flagger
wordpress_id: 194306
categories:
- DevOps
tags:
- Kubernetes
- progressive delivery
- test in production
- weaveworks
---

In August, Meetup invited us to host our Test in Production Meetup at its headquarters in NYC. Lena Krug, VP of Enterprise Technology at Meetup, got the evening started by heralding the benefits of deploying code early into production (we agree, Lena!). Then, Sebastian Bernheim, Customer Success Engineer at [Weaveworks](https://www.weave.works/), gave the first talk. He shared how Flagger, a Weaveworks solution, automates canary deployments to Kubernetes.


<blockquote>"You know exactly what version was released at any given time. You know exactly who released it. By the way, this commit is right there [[shown in demo]] on my Git Repo so I can see exactly what happened. That's the beauty of GitOps. It's basically using Git as a single source of truth, which I find very entertaining. I just happen to be a big Git fanboy." – Sebastian Bernheim, Customer Success Engineer at [Weaveworks](https://www.weave.works/)</blockquote>


Watch to learn how to simplify the operation of Kubernetes clusters with automated continuous delivery pipelines, observability, and monitoring. If you’re interested in joining us at a future Meetup, you can [sign up here](https://www.meetup.com/Test-in-Production/).

[embed]https://youtu.be/NdFGgAI0Gvk[/embed]

TRANSCRIPT:

Andrew Campbell, Techincal Account Manager, LaunchDarkly: Hey everybody. Thanks for joining us here at Meetup headquarters. My name is Andrew Campbell. I'm a technical account manager at LaunchDarkly. We are here for Test in Production, our first time here in New York. We've been doing Test in Production for about a year and a half now. This is our first time here. We had recently done one in London. We want to continue to expand these Meetups and promote the idea that your testing environment is no longer needed and it's a bit of an antiquated idea. I know it was a bit of a cowboy code concept a long time ago. We're really happy to see that it's becoming more and more of a best practice in the world of enterprise.

As usual, if you are a Tweeter and you like to Tweet things, we would love for you to use the hashtag #testinproduction. Let's think. What else? We're hiring, for all positions. We also have an office that's going to be starting soon in New York City. It's going to be good stuff. We have some of our wonderful new people over there. What else am I forgetting in my notes? That's right. If you have a phone, this is a Meetup, we do have presenters, if you could please remember to silence your phone because we don't want any distracting noise. With that, I'm going to hand it over to our gracious, Lena, from Meetup.

Lena Krug, VP of Enterprise Technology at Meetup: Hello, everyone. I'm Lena, I work for Meetup. I'm the VP of Enterprise Technology which is some fancy term or title. Welcome to Meetup HQ. This is where Meetup is headquartered. We have a little over 200 employees. Most of them are in this building, not necessarily on this floor. This is a space that we use to host Meetups. We have our all-hands meetings here. We love to have the community here.

A little bit about why I wanted to host this particular Meetup because I love testing in production. When I started working for Meetup, I guess, almost four years ago, I walked in the door, and I took a look at what was going on in terms of how we were delivering software to our customers and in production and how we were doing testing. To put it nicely, it was extremely bespoke and artisanal. It required a lot of manual effort of manipulating branches in Git and deploying them to weird staging environments and weird QA environments. We had feature flags, but we weren't using them as a mechanism to launch code early into production and turn it on for actual testing. We were just using it to turn features on and off for split testing and those kinds of things.

I knew early on that we had to shift that and we had to get into a place of doing continuous deployment. To me, continuous deployment straight in production requires a couple things. It requires a very solid foundation of testing within your testing pyramid, and it requires having feature flags so that you can launch things into production without your users seeing them or without your users being impacted by them so that you can iterate on them and test them until they're ready. We had our own, just like we had a bespoke QA process, we had our own artisanal bespoke feature flag system, right, which was great for the monolith that we were running but that didn't scale for us as we were starting to now build more microservices and more distributed systems so we knew that we had to evolve and we found LaunchDarkly, and we're glad we did. It's been a great value to us.

I'm not going to bore you with a lot of details. I wanted to give you a quick intro. We're hiring too, I guess. But, that's unimportant. I'm going to hand it off. Who's up? Sebastian?

Sebastian Bernheim, Customer Success Engineer at Weaveworks: Hello. I'm going to see if this actually comes up again. I've been a user of Meetup for a long time, a long-time listener, first-time caller. I've actually been on the platform long enough to have one of my accounts, at one point, banned from Meetup for reasons that were never clear to me. But, it was no big deal. I nuked that account and got another one. Now I've been using my Weaveworks account now to join up and come to Meetups. It's always fun and I'm glad to be speaking here for you today.

Today I'm going to talk about Weavework's progressive delivery system. We actually support an open-source project called Flagger that manages progressive delivery in Kubernetes. One of the fun things about Kubernetes is being able to get rid of nodes, get rid of Pods, repave your instances, and then pull them back up again. One of the problems with Kubernetes is that you can feel unsure about what's going on in your cluster at any given time.

At Weaveworks, we're known as the "GitOps Company." Our CEO and founder was a member of the Technical Committee for the CNCF and we have actually brought Flux into the CNCF fairly recently, and Flagger is a sandbox candidate right now. These are the components that are part of the system that I'm working on. I'm not going to read the slide because you can read faster then I can talk. This is, in general, Flux is an agent that runs on your Kubernetes cluster. What it does is it will look at your Git Repo for your YAML file definitions and then compare them to what's going on in the cluster. Anytime they deviate, it will fix it and put it back to what it finds so that when you want to make a change to your cluster, instead of using the kubectl command line, you'll use Git.

You'll check your change into those files, that way all of your changes are tracked in the Git file system. They're hashed. You can audit them. You know exactly who made what change, and when. Flux manages that for you from the perspective of the cluster so that you don't keep credentials outside somewhere else where they're easier to get and they're more exposed. The Helm Operator is part of Flux. This allows you to use Helm charts instead of YAML files. It's very simple. Flagger is the tool that will take changes that are applied to your deployments. Say you want to deploy a new image of something, it will detect that change and then it will do a canary deployment for you automatically. We'll talk about that in a minute.

Cortex is our Prometheus-based service. This is for time-series databases for showing you statistics which you'll see how important it is in a minute because, in full disclosure, I'm actually a working engineer, yesterday I managed to completely bork my demo cluster. What I'm going to show you today is actually broken. It will be fun. I'll have to have you use your imagination to imagine what it would look like if it actually worked. This is a diagram that shows what Flux ... I'm a firm believer that once you've seen one UML diagram, you've seen them all. This is really not that different but you get a sense of how things fit together in the GitOps model.

Your user is that playschool-looking guy over there committing changes into Git as I mentioned before. Those changes are picked up by the Flux CD system and then applied to Kubernetes API and tracked in Memcached so you can keep track of what images are running where and then those are copied into the cluster and then they run. Let's just pretend that Docker image isn't there because I don't feel like getting into it but that's basically Flux wall so watch your Repos to see when you get a new release of an image so you can automatically deployed if it fits a certain pattern. All kinds of that stuff. The Helm Operator basically does the same thing except you're using Helm and Tiller to make those changes instead of simply using YAML files in your Git Repos. It's the same idea applied to the Helm and Tiller model.

Flagger is the system I am here to talk about today. In addition to Flagger, we actually have a software as a service hosted platform called Weave Cloud. The people will signup for the hosted service that includes hosted Prometheus-hosted Cortex and that will enable them to monitor Kubernetes cluster from the platform. Flagger is the component that runs behind that. That actually will manage the canary deployment for you. What it's doing is it's using the service mesh that runs in your cluster to manage the traffic that goes between one deployment and another. Say you're running Happy Service 1 and you decide that you want to upgrade Happy Service to Happy Service version 2. You start out with your primary, which is running Happy Service 1, and you check your change into Git to say I want to change the image from Happy Service 1 to Happy Service 2, and Flagger will set up a second deployment of your Happy Service, which we call the canary.

I like that analogy because it brings to mind the coal miners that go down in the mine and they bring the little canary with them. In this case, instead of sacrificing the canary, you're going to sacrifice a small subset of your users. Just imagine them laying out on an altar, and you have the knife. They're the ones who are going to get hit with the new version of your software; maybe it works, maybe it doesn't. In this case, you're limiting the blast radius to only those users that you're willing to take the knife to in order to limit the exposure if something does go wrong.

Flagger sets up the two versions of the service and it uses the service mesh then to direct traffic from the main service to the new service in small increments, say 5% at a time. Then it will increase those increments for a period of time until it reaches a threshold that you define, say 50% of all the traffic. Once it reaches that threshold without experiencing a lot of errors, and you can also set the threshold at how many errors it would experience before it gives up and rolls back, if it reaches that threshold successfully then it will cut over all of the traffic to the new service and then that service becomes the primary and the old ones becomes your canary.

That's basically the idea. This deployment and services, if you're familiar with Kubernetes, the deployment is the thing that lives behind the service that does the actual work. Down here you have your Prometheus Interface. Prometheus is where all that success and failure, all those statistics go to. That's part of the thing I broke. The Kubernetes API is what Flagger interacts with in order to set up all these resources. Without further ado... oh, actually there is some further ado.

Here are the release strategies that it supports. Canaries, as I said, where you sacrifice a small percentage of your users to see if they're going to get an error or not. A/B testing, which allows you to switch between positive and negative, and then Blue/Green which is the same kind of idea, but it's just a traffic switching. For A/B testing you can route different people to different parts of it based on whatever, headers, cookies, the phase of the moon, or their favorite color. Whatever information you can get about them.

Any questions? I know I talk fast. I like talking fast, but there's some ground to cover and this is really the boring part.

Audience: I have a question actually. There is a system in Flagger and you guys got integration with cloud with Flagger?

Sebastian: Yes. What I'm actually going to show you is, I've set up the demo cluster as an EKS cluster so it's using Amazon's App Mesh ...

Audience: Okay thanks.

Sebastian: ... as the service mate. We also work with straight STO ...

MC: Sorry, you can ask questions on this if you'd like.

Sebastian: Oh yeah. It's the easy button.

Audience: Do you guys also got any plans of having Flagger with ECS or something like that?

Sebastian: Flagger will work with any cluster you set up or whatever platform you set your cluster up on. I'm using an EKS cluster because I'm also testing our EKS cuddle tool as one of my functions and it was just easier for me to kill two birds with one stone. You can do this on GKE. You can do this with your own on-prem cluster. I've seen people run this demo with Mini Cube. I don't like running it with Mini Cube because, honestly, it falls over more than the rest of the demos. Even though I'm going to show you the broken one today, it's more likely to completely flame out in the middle of a demo. I tend to use the hosted platform.

By and large, just as a philosophy, Weaveworks tends to be very agnostic. You can swap out different portions of this. If you have a different service mesh that you want to use, we work with a couple of different types. I actually have a demo coming up next week with a company called Aspen Mesh that does their own service mesh layer on top of SDO that we're working on an integration with. I'm spacing on the name of the other main service mesh that's out there but SDO is the main one and you find a lot of implementations are based on it.

Audience: Linkerd is what?

Sebastian: That's what it is, Linkerd, yeah. Stephan, who is the main developer, he's in Romania so he couldn't be here today because that's where he lives and he gets tired of having to leave there all the time. He fairly recently finished the Linkerd integration and that was released ... Demodee, you can correct me, but it was about a month and a half, two months ago?

Demodee: Yeah.

Sebastian: Yeah. This is the fun part of the presentation where I show you my broken system. I'm just going to switch over. This here is our software as a service hosted platform. It's managing your cluster, three main application portions; explore, monitor, and deploy. Explore, in general, and I'm not going to go too far into this because I want to get to the progressive delivery part, but Explore lets you see from a high perspective what's happening on your cluster. That's a graph of the nodes.

Here's a graph that shows you your Pods. You can filter them based on this kind of thing. I'm going to show you the Flagger Pods. There's only one so it's not that dramatic. You can dig into see details about the Pods. You can see the consult to get your logs off of it. Oh good, that's not just covered in errors.

Audience: Right now, your Flagger port isn't managing anything?

Sebastian: Right now, it's not merging anything. It's just sort of sitting there. My application, as an example application, I'm running something called Pod Info. This really just is a little web service that publishes its own version in a pretty little screen, because I broke my service mesh. I can't show you the screen but it's basically just for Version 2.1, it will show you a little red screen and for Version 2.2, it will show you a little blue screen. That's the general idea. I'm going to show you a release of that in a few minutes.

The Explorer interface lets you see from a high view of what's running on your cluster. You can see in this case, we have two containers running in two Pods, Pod-info and Pod-info 2. They're both running Pod-info D. But if we were to go take a look at the workloads, we would see that within this service, we have Pod-info and Pod-info primary. Pod-info is the canary, and Pod-info primary is the running instance in this case. You can see the two Pods are running for Pod-info primary and there are no Pods running for Pod-info.

What I'm going to do is I'm going to go to our deploy interface. Now, you can also do this just with straight Git. This basically is just an interface on top of the YAML. Rather than actually open up a YAML file and make a change to the file and then check it in to get ... this is an interface that will do that for you. It takes a look at the versions of the image that are out there on the image Repo, and it lets you pick which one you want to release. Just because it's faster and slightly more entertaining to do it this way, what I'm going to do is I'm going to release version 2.12. This will be our progressive release.

What's going on in the background here is when I hit this release button, the Flux agent is going to check in a change to the Git repository. All it's going to do in that change is change the version number of the Pod info image, that's running in the Pod info deployment. What's going to happen on the back end is that we have a CRD, a custom resource definition, called canary, that runs in the cluster. I've set up a canary instance for Pod info, which there isn't really a fun, graphical way to show it, but this is in general what it is. This is the Pod info canary description. You can see it has all kinds of fun attributes to it, which I won't dig too far into, but one of the things that it does is it runs this little command here. This is what's going to beat on Pod info, to see whether things are going to fall over or not.

You can either use your natural traffic, which is coming from your users, or you can run something like, hey, which will just create load on the cluster for you so you can tell whether the deployment is going to be successful or not. Going back to this part of the interface, I'm going to hit the release button. What we'll see here is when I do that, it's going to take me ... now this is the brand spanking new pretty portion of the interface that will display what's going on. Normally, when we would do this demo I would just pull up a terminal and I would exec into the Flux Pod, the Flux container, and you would just watch the log files go by. This is slightly more entertaining. You can see that the deployment has X number of old Pods versus X number of new Pods that are ready.

Right now, what it's doing in the background is Kubernetes is spinning up. It's really just checked in a change to Git Repo, and Kubernetes is now spinning up through the canary CRD, new versions, the versions of the new Pod. Unfortunately, because of the fact that I broke the deployment, it's not publishing any statistics. What I broke on the deployment, by the way, is the core text and the Prometheus part of it. Now, because in this demo it doesn't know how much successful traffic versus how much failure traffic, unfortunately, all my deployments are going to fail. You'll just have to let me do a little hand waving. In general, this is what it looks like. You just have to imagine that it would either succeed or fail.

What happens in the background is it's actually watching the statistics to get published by the two containers. Then it will compare those stats against your thresholds in Prometheus, which is something that would normally trigger an alert, for example, that would go up on your Slack channel, would show up on your pager. This would actually indicate to Flagger whether the deployment has succeeded or failed. It's going to watch the traffic. Then slowly, it will increase and decrease the traffic that goes across the two nodes, the two versions of the Pods. It will increase that traffic by 5% every, I don't know, 30 seconds I think, is what it's set to right now.

Now, because it's not getting the statistics, it's just going to think that it failed and so it's going to roll it back. This all happens for you automatically. If we were to go look at the Repo, and I can do that, I can go here into the resources view and go take a look at the history for the Pod info container, and see that this was the check in that I just did a few minutes ago with the commit. Then what it did was it committed that to Git, it synced that to the cluster. Then the deployment actually has the new version of it. Because the canary resource was watching this release, the canary resource said, "Okay, I'm going to make the Pod info canary portion of it the new version," and then the deployment you'll see actually has the new image tag on it. This is a check in into Git. That's basically exactly what happened on the back end when I did this deployment. It replaced 2.1.0 with 2.1.2. That's it.

This way, you know exactly what's running in your cluster at any given time. You know exactly what version was released at any given time. You know exactly who released it. By the way, this commit is right there on my Git Repo so I can see exactly what happened. That's the beauty of GitOps. It's basically using Git as a single source of truth, which I find very entertaining. I just happen to be a big Git fanboy.

If you were to go into here and take a look at the Pod info workload, you can see that the current released version is 2.1.2, but that version was rolled back. We can also do this again. We can go straight back to 2.1.0 and run the canary release. Now, those numbers there you can adjust based on whatever version you want. Here, you can see a small graph that shows you the weight of traffic that's going back and forth between the primary and the secondary Pods. You can see that that last release there, it shifted 5% from the primary to the canary. Then it rolled back because it's not getting statistics and it thinks that the release has failed. Down here, you can see the statistics it's not getting. Normally, there'd be a little graph there showing you what the request volume would be. Then that would slowly transition from the main deployment to the Pod.

That's basically the whole point of it. This here is a [Graphona] dashboard, which is normally very entertaining to show, but right now it's all red because, again, I broke the cluster. Go away, errors. Thankfully, this is just for me to run demos and is not any kind of a production system, because if it was then I would be yelled at for testing things in production. Not to ruin the theme.

Audience: Yeah, you need a cluster.

Sebastian: That's right. I need a cluster to test the cluster. That's right. That's pretty much it. That's the extent of the demo. It would be more exciting if I could show you a success and a failure, but unfortunately today, I can only show you the failure. Yes?

Audience: This dashboard you were showing, that's a view on top ... well, it's something on top on Flagger?

Sebastian: Yeah. This is a visualization layer. That's the Weave Cloud interface, and it's our software as a service hosted platform. The reason that I use it is just it's easier to look at and understand than just watching the log files go by.

Audience: That's what Flagger is really doing, what you're showing?

Sebastian: Yeah. Flagger was actually doing in the background, it's managing the release. This is really just a visualization tool that shows you what's happening.

Audience: Yeah, so you can just manage the whole thing while Flagger or the JSON, well, it can really manipulate the JSON?

Sebastian: Yeah. That new interface that I showed you is that canary deployment button and the little graph that shows you the transitions. That's Weave a couple weeks. What's that?

Audience: Where you can manage the weight of the traffic?

Sebastian: Yeah. I can show you again the release screen.

Audience: Because you were imagining the way through the Canary path?

Sebastian: I think this should have already failed, so that should be safe to do. Even if it's not, that's my demo cluster. I'll pave it over tomorrow if I have to. Going back to the Pod info, deployment. If I hit this Canary release button, using feature flags, this is a feature that we turn on and off. Right now it's only being used by a couple of early adopters who are willing to accept that sometimes it doesn't work. This is a feature that we've released fairly recently that's a UI on top of the Flagger tool. The Flagger tool just does what I talked about before. All it's going to do is it's going to take a look at when you make a change to the image version of one of your deployments. Then it's going to create that canary deployment for you, and use the service mesh to direct traffic between one and the other according to your thresholds and your schedule. That's about it.

Sebastian: The whole thing is configurable. You can change the statistics that it bases its decisions on. You can change the steps of how much traffic it increases or decreases. You can change the threshold when it decides that the release has been successful. That's all visible here. The max weight is how much is at the point at which it decides its success. The threshold is where it says that the failure is going to be too much. Then this is the minimum weight, that's where it starts. Then the step weight is how much it increases or decreases.

You also select the version that you want to release. You can roll forward or you can roll back. Then you hit the canary release button and it starts the whole process. Flagger only ... all this is really doing is you're checking in a change to the canary definition, which is in itself also a file in Git that tells the canary release what to do. This is a YAML file that is pretty much defining for the Pod info canary release, what you want to release on top of what. You don't need to use the UI, you can, it's just that it's much more interesting to look at than...putting into YAML files.

Audience: Absolutely. No, thanks. This file is really the YAML file for Flagger really?

Sebastian: Yeah. This is a Canary custom resource.

Audience: Yeah. Okay.

Sebastian: This is what Flagger uses to manage that release.

Audience: This is a CRD for the Flagger?

Sebastian: Pretty much. Well, the CRD is its own definition. It's like the spec. This would be one instance of that.

Audience: Okay. Cheers, thank you.

Sebastian: Yeah. That's basically Flagger in a nutshell. It would be more interesting if I could show you a success release again, but unfortunately today I can only show you a failure. At least you know now that if your release does not go well, Flagger will automatically roll back to you to the previous version, and then you won't have too many people impacted by a release that suddenly starts producing hundreds of 500 errors, which I've done personally, and had to wake up at 3:00 in the morning to fix. It's nice to not have to do that.

Here is the pretty Graphona dashboard. It's actually this is really just Graphona running in the cluster that I've got a TOML set up for. Normally you'd be able to see some pretty statistics here in addition to the Weave cloud interface. Today, I've decided to make it explode. If you're interested in Flagger and you want to see more details about it, it is an open-source project. You can contribute to it, you can read the code, you can find out all about the definitions. The website is Flagger.app. We also have a few tutorials for setting it up on the Weave cloud website. If you go to Weave.works, and then go to the documentation section, there's a whole section for Flagger where you can find out all of the details that you ever wanted to know and more. That's it.

This is another one of those annoying diagrams, which describes the GitOps pipeline. This is the concept of GitOps where you check your changes into Git. Then they get fed into Flux, which get fed into Flagger, which make a change to the canary definition. Then that's managed through the direct traffic back and forth. The concept of GitOps I find very powerful because I just really like Git. I like the fact that it tracks everything and then its egalitarian code versioning system. That's part of what makes me a fan of Flagger and a fan of the Flux component. Flux by the way, also is an open-source component. If you have any questions about it I'll be happy to talk.

Audience: Yeah, can you explain a little bit about Flux? What was Flux doing here?

Sebastian: My favorite way to describe Flux is magic.

Audience: What? Sorry? Say again.

Sebastian: Magic. What it's really doing is it's just comparing in the same way Terraform would, the state of what's on your cluster to the clarity of description that you've got up in the Git Repo.

Audience: All right, so it's just so...?

Sebastian: Yeah. The idea of GitOps is applied to Kubernetes. Flux is the operator that makes those changes, but the concept of GitOps can be applied to any sort of infrastructure layer, as long as you have a way of declaring the infrastructure and comparing it against what's in the real world, what you've actually got deployed. Rather than actually going and making those changes manually, say you had a Terraform file that was describing how you would set up all of your AWS resources, this would be an operator that compares those declarative descriptions against what you've actually got deployed and then applies them if there ends up being a difference, prevents you from having drift and it gives you a way of auditing everything that happens.

Audience: Where does it store the state?

Sebastian: Flux stores the state ... primarily your state is described in the Git Repo, but Flux also makes a clone of the Git Repo locally that it will use to compare, to make sure decide whether it needs to pull or not. You don't want it to pull every 15 seconds. Maybe it would be several megabytes of pull. It also has a local clone of your repo. Then that basically represents the state. To find out the real state, of course it interacts with the Kubernetes API. We have another one.

Audience: All right, so when you're going between different versions, is it acting as the primary load manager? Is it relaying it to a third party load manager, or it's just simulating traffic to one of those?

Sebastian: Depending on what you mean by the node manager, Kubernetes is actually managing the nodes that are running. It'll bring up and bring down Pods as it needs them. The service mesh actually directs the traffic in between the two versions of the Pods. Kubernetes is really just instructing the service mesh, "Hey, I want 5% of the traffic to go here and I want 95% of the traffic to go here." Then 10%, 90%, and so on until...threshold.

Audience: My question is from the interface you showed, where I can vary load to this specific version, or you have the small interface where you could ... yeah, is it taking over as a manager for that or it's relaying it to Kubernetes?

Sebastian: It's relaying basically. The main port, Flux itself is really a communication and management agent. The real work is being farmed out mostly to Kubernetes in the service mesh. Actually directing the traffic and deciding what goes where. Whatever kind of a switch your service mesh supports, you can generally do within the operator, within the canary custom resource.

Audience: Okay, cool. Thanks.

Sebastian: Nope? Going once, twice, three times. Okay. I'll be here all week. Tip your waitress. I'm really just looking for who I hand this to now. Here you go.

Andrew: Thank you, Sebastian.
