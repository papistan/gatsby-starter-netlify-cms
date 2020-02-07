---
author: matkins
comments: false
date: 2018-03-19 16:20:38+00:00
layout: post
link: https://launchdarkly.com/blog/go-serveless-not-flagless-implementing-feature-flags-in-serverless-environments/
slug: go-serveless-not-flagless-implementing-feature-flags-in-serverless-environments
title: 'Go Serverless, not Flagless: Implementing Feature Flags in Serverless Environments'
wordpress_id: 1510
categories:
- Feature Management
tags:
- AWS
- feature flags
- Lambda
- LaunchDarkly
- serverless
- webhook
---

### A demonstration of LaunchDarkly feature flags with AWS Lambda


Serverless architecture, while a relatively new pattern in the software world, is quickly becoming a valuable asset in a variety of use cases.

There are some notable business advantages to serverless architecture:



 	
  * Faster development – easily harness existing backend services and third party APIs to quickly build and deploy apps

 	
  * Lower cost – substantially decreased operational costs by not having to manage infrastructure in addition to the componentization of the entire application (only scale what you need to scale)

 	
  * Less maintenance – scaling, load balancing, and patches are a thing of the past, serverless platforms take care of it all for us


Coupled with feature flags, a serverless application allows teams to control feature releases without having to redeploy. This is especially useful for serverless applications that tend not to focus on persistence and be more stateless in nature.

In this article, we’ll start with the assertion that you have already decided that serverless functions makes the most sense for your application architecture. What you really need is the ability to continue using feature flags in this type of architecture. This is where LaunchDarkly has got you covered.

We’re going to look at how to integrate LaunchDarkly into an application running on AWS Lambda. [AWS Lambda](https://aws.amazon.com/lambda/) lets you run code without provisioning or managing servers. On the other hand, LaunchDarkly is a feature flag management platform that allows you to easily create and manage feature flags at scale.

For smaller workloads, you can use the LaunchDarkly SDK as you normally would. Evaluating a feature flag with the nodejs runtime in AWS Lambda looks like this:

    
    var LaunchDarkly = require('ldclient-node')
    var ldClient = LaunchDarkly.init(process.env.LAUNCHDARKLY_SDK_KEY)
    var ready = ldClient.waitUntilReady()
    
    exports.handler = (event, context, callback) => {
    
        ready.then(() => {
    
           /*
                ...evaluate your flags and do your work here...
    
            */
            callback()
        }, callback)
    }


This naïve approach is appropriate for serverless workloads that have limited concurrency (e.g., a scheduled job). If you have a workload that has high levels of concurrency or sensitivity to cold starts, this approach will have poor cold start performance because we need to call out to LaunchDarkly whenever a new [Execution Context](https://docs.aws.amazon.com/lambda/latest/dg/running-lambda-code.html) is created. To overcome this, we need to add a second Lambda function, an API Gateway, and ElastiCache to build a serverless flag storage pipeline. We’ll use this pipeline to maintain a store of feature flag configurations so that the application can just get flags from redis and avoid a more costly cold start.


#### Storing Flag Configurations


**UPDATE: **We've gotten some great feedback that has pointed out that by using ElastiCache, we're hurting the cold start time. In order to use ElastiCache, you must put your lambda function in the same VPC as the cache. This causes an ENI to be created on cold starts, which can actually be slower than calling LaunchDarkly. We're working on [an alternative using DynamoDB](https://github.com/launchdarkly/node-client/issues/88). The methodology below is still useful if you want to isolate your lambda functions from LaunchDarkly.

AWS turns out to be a well-equipped platform for serverless feature flagging. In our implementation, we create a [webhook ](http://docs.launchdarkly.com/v2.0/docs/webhooks)in LaunchDarkly to hit an [API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-create-api-as-simple-proxy-for-lambda.html) endpoint which acts as a trigger for invoking a lambda function.[![](https://blog.launchdarkly.com/wp-content/uploads/2017/04/webhook.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/04/webhook.png)

Then, the lambda function can have LaunchDarkly populate a Redis ElastiCache cluster by initializing its SDK with the built-in “RedisFeatureStore” option. This lambda function built on the NodeJS runtime would look something like this:

    
    var LaunchDarkly = require('ldclient-node');
     
    exports.handler = (event, context, callback) => {
        var redisConfig = {
            port: process.env.ELASTICACHE_PORT,
            host: process.env.ELASTICACHE_ENDPOINT
        };
        var store = new LaunchDarkly.RedisFeatureStore(redisConfig));
     
        var ldConfig = {
            feature_store: store
        };
        var ldClient = LaunchDarkly.init(process.env.LAUNCHDARKLY_SDK_KEY, ldConfig);
     
        ldClient.once('ready', () => {
            ldClient.close();
            callback(null, 'store updated');
        });
    
    }


Note that we’re initializing the LaunchDarkly SDK inside the handler. That’s because, by initializing the SDK, we’ll pass the update that triggered the webhook along to the redis store. Generally speaking


#### Processing Feature Flags


Now that our flag configurations are neatly stored in the Elasticache cluster, we need to change our naïve Lambda function to retrieve and process flags without waiting for any outbound connections to LD! This is achieved by enabling [LaunchDarkly Relay mode](https://github.com/launchdarkly/ld-relay#daemon-mode) in the SDK options. The function’s “event” parameter can be used to pass in a user to be evaluated by the LaunchDarkly SDK.

    
    var LaunchDarkly = require('ldclient-node');
    
    var redisConfig = {
        port: process.env.ELASTICACHE_PORT,
        host: process.env.ELASTICACHE_ENDPOINT
    };
    var store = new LaunchDarkly.RedisFeatureStore(redisConfig);
    
    var ldConfig = {
        feature_store: store,
        use_ldd: true
    };
    
    var ldClient = LaunchDarkly.init(process.env.LAUNCHDARKLY_SDK_KEY, {ldConfig});
    
    exports.handler = (event, context, callback) => {
        /*
            ...evaluate your flags and do your work here...
        */
        callback();
    };




#### Take Aways


It’s important to understand that there are multiple ways to implement feature flags in your serverless architecture. The method will depend on your app’s structure, your serverless provider, and your implementation timeline. You can check out this [guide](https://github.com/launchdarkly/featureflags) to feature flagging for best practices and ways to get started.

_Originally published on April 14, 2017 by Justin Baker. Updated on March 19, 2018 by Mike Atkins._
