---
author: johnkodumal
comments: false
date: 2015-08-05 19:00:47+00:00
layout: post
link: https://launchdarkly.com/blog/can-we-stop-pretending-that-docker-is-great-for-development-environments/
slug: can-we-stop-pretending-that-docker-is-great-for-development-environments
title: Can we stop pretending that Docker is great for development environments?
wordpress_id: 113
categories:
- Continuous Delivery
- DevOps
tags:
- development environments
- Docker
---

**tl;dr: It makes perfect sense to run backing services (databases, caching, storage, etc.) in Docker, but if you use a compiled language, Docker's not the way to go for local development.**

Every six months I try to use Docker for local development. I tried again recently, and found (once again) that the technology still isn't ready. But this go-around I reached a further conclusion— for most development stacks, running Docker for local development is a pointless exercise. It introduces complexity and provides almost no benefits.

The crux of the problem is this: achieving an efficient edit, compile, run cycle means that your development container will not be the same as your production container. This negates one of the primary advantages of using containers. Furthermore, you will never make your edit, compile, run cycle as efficient or foolproof as running locally without a container. This means that you're paying a containerization tax and reaping none of the rewards.

Let's first look at my claim that an efficient edit, compile, run cycle requires separate "non-production" container definitions. First, assume otherwise. If you're using your production container for development, your container must contain a pre-compiled artifact of some kind, or you're doing something crazy like running the compilation in your `Dockerfile`. In either case, you need to re-build your container every time you make a change. Your E/C/R cycle looks something like this:

    
    docker-compose up -d # start all your containers, and leave them running
    # edit myservice
    make myservice # or whatever you do to build myservice
    docker-compose build myservice
    docker-compose restart myservice


We went down this path, and found that the cycle took long enough (> 30 seconds, excluding the build time for the service itself) to trigger a boredom-induced context switch. This is a productivity killer.

You can argue that this is an implementation critique, and that (eventually) this cycle will be much faster, but to compete against local development, the build /restart steps need to be nearly free. They're not, and I don't think they're ever going to be, even with efficient use of the Docker image cache.

If you're willing to discard the idea of using your production containers for local development, or you run an interpreted stack that has no build process, you can change the rules of the game. You can mount your repository directory into the container, listen for file changes, and use a live reload tool (e.g. [Fresh](https://github.com/pilu/fresh)) to re-compile and re-launch your application within your container.

With some tomfoolery, this works reasonably well. It took us time to find and set up [docker-osx-dev](https://github.com/brikis98/docker-osx-dev) to mount and sync source folders efficiently, and several hours of putzing around with `boot2docker` to get `inotify` working properly, but we did arrive at a working solution.

But when we stepped back and looked at the beast we'd birthed, we could find no compelling advantages to it. We had been using `foreman` to start all our services locally, and `foreman start` is incredibly fast compared to `docker-compose up`. We inherited all the added complexity of managing `boot2docker` in addition to the Docker containers themselves. Our setup documentation tripled in length.

[![full-docker](https://blog.launchdarkly.com//wp-content/uploads/2015/09/full-docker.jpg)](https://blog.launchdarkly.com//wp-content/uploads/2015/09/full-docker.jpg)

Our original motivation for trying Docker for local development was an errant `brew update` that broke some of our critical services locally (memcached and elasticsearch). In the end, we decided that running these backing services via `docker-compose` made plenty of sense, and do end up simplifying setting up and running a local development environment. On the other hand, we moved back to running our own microservices locally via foreman. We haven't looked back since.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._
