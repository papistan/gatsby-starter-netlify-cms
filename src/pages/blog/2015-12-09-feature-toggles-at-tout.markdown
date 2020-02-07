---
author: andreaech
comments: false
date: 2015-12-09 00:35:27+00:00
layout: post
link: https://launchdarkly.com/blog/feature-toggles-at-tout/
slug: feature-toggles-at-tout
title: Feature Toggles at Tout
wordpress_id: 278
categories:
- Continuous Delivery
- Feature Management
tags:
- feature toggle
- feature toggles
- internal testing
- javascript
- microservices
- Ruby on Rails
---

_How [Tout](http://www.tout.com) uses feature toggles in their development process, guest post by [Javid Jamae](http://www.twitter.com/javidjamae), Principal Engineer (Growth at Tout)._


Tout is a video platform for media brands and content publishers. We have video players on hundreds of prominent high-traffic media websites and blogs across the United States. Using our video marketplace, websites can show premium video content from producers such as Time, Yahoo, Condé  Nast, The Wall Street Journal, ESPN, and dozens of others. The sites can also let their journalists and authors capture their own video content using our Android and iOS apps, and then play their content on their sites. 

The way our service works is that we provide a Javascript embed code that our partner sites place within their website template. When their page loads, we inject our video players into various parts of the page. Deciding everything from where the video players placed, what video content it has, and how it appears can be decided on the server side, thus minimizing configuration and code changes for our customers. 

In the early days, we only had a few sites using our new products. To keep things simple, we kept most of our product configuration in the code and consistent across all of our partner websites. When we wanted to make a change, we would negotiate with all of them before rolling out a new feature. This was manageable because there was little to no variability and notifying  individual partners of changes was easy. 

As our customer base grew, we found it increasingly difficult to maintain a single product configuration, so we introduced a way to configure products differently for each partner website. But, due to the nature of being an embedded product, we started finding it difficult to test changes internally and to demonstrate changes to our partners.

We did internal testing using a web debugging proxy software called Charles. We would deploy an updated version of our code to our staging (i.e. internal test) environment, then we would configure Charles to proxy our production server to our staging server on the machine we were testing on. Though there are a few snags with this process, it works relatively well overall. The problem with this approach is that it only works for internal testing.   

Our customers often wanted to preview new changes to their site before we rolled them out so that they could do their own verification and training. As the demand for customer previews increased, we started looking into feature toggles as a solution. 

Conceptually, feature toggles are simple, you just keep the old version of your code in place, but wrap it in a conditional clause that does the new thing if the feature is enabled:

    
    if feature_enabled("blah")
      run_new_code()
    else
      run_old_code()
    end


Since we are using Ruby on Rails, we started by using a Ruby library appropriately called 'feature'. The feature library is [an open source library hosted on Github](https://github.com/mgsnova/feature). The great thing about this library is that it enabled us to create feature toggles in our code within minutes.

Using this library had several downsides as well. Since it's just a library, it has no user interface for creating or modifying feature toggles. It also has no functionality for passing in feature toggles from web browsers using request parameters or cookies, which is tremendously useful for testing a specific state of your toggles. Another thing that is missing is metadata around when and who modified the state of the toggles, which is really useful for debugging and forensic purposes. Nevertheless, with a bit of work building out those tools, the feature library was great for getting up and running and we were able to deploy our code to our production with a new feature toggled “off” and then enable it for testing or demo purposes.

[![feature switch](https://blog.launchdarkly.com/wp-content/uploads/2015/12/feature-switch.jpg)](https://blog.launchdarkly.com/wp-content/uploads/2015/12/feature-switch.jpg)

After starting to use feature toggles, we realized several unintended benefits. First, if we found any issues with the new version of the code, we could merely roll back to the old version by switching a toggle. We no longer needed to do roll-back or roll-forward deployments to undo a mistake in production. 

Another great benefit was that it minimized environment contention. Since our team is still relatively small, we only have one test environment. By using feature toggles, everybody could merge and deploy their changes to the staging environment and just toggle “on” the features that they want to test by setting cookies in their browser. 

We also started using feature toggles as a way to do zero-downtime feature cutover. Since we're using a microservice architecture, we have multiple systems that all talk to one another. Previously, if we needed to roll out a new feature that required communication between multiple systems, we would have to bring down all of the related systems and deploy all of the appropriate code changes before bringing the systems back up. But with feature toggles, we were able to deploy each system code change when it was ready and then just synchronize toggling the new functionality on. Effectively, this eliminated the need to have complex blue-green deployments since we just managed it all with feature toggles.

However, using toggles comes at a cost, though I feel like the cost is definitely justified. First, not all of our developers were thrilled about having temporary if/else statements littered throughout the code. They felt that this added extra complexity in the code and in the unit/integration testing effort. We started developing some good best practices around where to put the feature toggles and updated our development process to include the proper removal of features that had already been rolled out. While unit testing did become more complex, the overall complexity of our process was simplified. We no longer required as many unnecessary feature and merge branches and the deployment and process became simpler as I mentioned earlier. 

All in all, I'd say that using feature toggles has been a great tool in our tool belt and has had significant positive benefits to our development process. Though we used an open source library and grew the tools that we needed around it, tools like [LaunchDarkly](https://launchdarkly.com/?utm_source=launchdarkly_blog&utm_medium=organic) (which didn't exist when we got started) would quite possibly have gotten us to where we needed to be much faster by providing us with all the tools that we had to build from the ground up and the support that we didn't have.  
