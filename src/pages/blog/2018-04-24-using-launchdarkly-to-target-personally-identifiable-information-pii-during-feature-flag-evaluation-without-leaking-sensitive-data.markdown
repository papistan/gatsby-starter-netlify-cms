---
author: Guest
comments: false
date: 2018-04-24 16:31:41+00:00
layout: post
link: https://launchdarkly.com/blog/using-launchdarkly-to-target-personally-identifiable-information-pii-during-feature-flag-evaluation-without-leaking-sensitive-data/
slug: using-launchdarkly-to-target-personally-identifiable-information-pii-during-feature-flag-evaluation-without-leaking-sensitive-data
title: Using LaunchDarkly To Target Personally Identifiable Information (PII) During
  Feature Flag Evaluation Without Leaking Sensitive Data
wordpress_id: 2453
categories:
- DevOps
- Feature Management
tags:
- feature flag
- feature management
- PII
- security
- sensitive data
---

_Originally published [here](https://www.bennadel.com/blog/3425-using-launchdarkly-to-target-personally-identifiable-information-pii-during-feature-flag-evaluation-without-leaking-sensitive-data.htm) by Ben Nadel on March 22, 2018. _

At [InVision](https://www.bennadel.com/invision/co-founder.htm?redirect=https%3A%2F%2Fwww%2Einvisionapp%2Ecom%2F%3Fsource%3Dbennadel%2Ecom), we've been using [LaunchDarkly](https://launchdarkly.com/?source=bennadel.com) as [our feature flag service provider](https://www.bennadel.com/blog/2943-using-launchdarkly-with-coldfusion-and-javaloader.htm) for the last few years; and, it has completed changed the way that our teams think about feature deployment. But, we've been using LaunchDarkly for so long that we've missed out on a lot of the new features they've added since their inception. As a member of InVision's Security team, one feature that I find particularly compelling is the ability to mark certain user data as "private". This allows Personally Identifiable Information (PII) to be used in rule targeting without requiring said data to leak-out beyond the boundaries of the application.

[embed]https://vimeo.com/261298109[/embed]

The most difficult part about using LaunchDarkly is understanding how user targeting actually works. What you have to wrap your head around is the fact that the LaunchDarkly client doesn't actually keep a database of users in your application - it only keeps a database of targeting rules. These targeting rules are synchronized with your application's local cache using asynchronous streaming. Then, these targeting rules are evaluated inside the boundary of your application based on the user objects that you provide at runtime:[![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-feature-flag-evaluation-rules-1024x647.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-feature-flag-evaluation-rules.png)

One of the benefits of this approach is that you can design targeting rules that depend on information of which only the client has knowledge. For example, we can design targeting rules that look at a user's email address even if we mark the "email" field as "private" such that it never gets sent to the LaunchDarkly servers. This is what allows LaunchDarkly to safely target Personally Identifiable Information (PII).

To this in action, I've created a simple node.js script that evaluates a feature flag against a user object that contains an email address. However, in my LaunchDarkly client configuration, I'm denoting the "email" field as "private". This means that the actual email of the user object won't be sent across the wire to the LaunchDarkly user database.
















    
    // Require the core node modules.
    var config = require( "./config" );
    var chalk = require( "chalk" );
    var LaunchDarkly = require( "ldclient-node" );
     
    // ----------------------------------------------------------------------------------- //
    // ----------------------------------------------------------------------------------- //
     
    // NOTE: Internally, the LaunchDarkly client will set up an INTERVAL, which will hold
    // the node.js process open until you explicitly .close() the client. In a long-running
    // application, this doesn't matter. But, in a "test" script, just something be aware of.
    var launchDarklyClient = LaunchDarkly.init(
    	config.launchDarkly.apiKey,
    	{
    		// By marking the "email" as a "private" field, it allows us to incorporate the
    		// email value in local targeting rule evaluation without actually sending the
    		// email address beyond the boundary of our application. Since an email is
    		// considered to be PII (Personally Identifiable Information), hiding the email
    		// may be important for your security audits.
    		// --
    		// NOTE: This can also be done on a per-variation basis by using the
    		// "privateAttributeNames" property in the "user" object.
    		private_attribute_names: [ "email" ]
    	}
    );
     
    launchDarklyClient.waitUntilReady().then(
    	function checkFlagValue () {
     
    		var flagEvaluation = launchDarklyClient.variation(
    			"can-see-cool-feature",
    			{
    				key: "test-user-1",
    				firstName: "Ben",
    				lastName: "Nadel",
    				email: "ben@bennadel.com" // <--- !! Personally Identifiable Information !!
    			},
    			false // Default / fall-back value.
    		);
     
    		flagEvaluation.then(
    			( flagVariation ) => {
     
    				var colorize = ( flagVariation === false )
    					? chalk.red
    					: chalk.green
    				;
     
    				console.log( colorize( "Can see feature: " + chalk.bold( flagVariation ) ) );
     
    				// After a pause, let's evaluate the feature flag variation again to see
    				// if the targeting rules have changed.
    				setTimeout( checkFlagValue, 1000 );
     
    			}
    		);
     
    	}
    );






 As you can see, we're evaluating the feature flag every second. This way, we can see how the evaluation changes over time as we manipulate the LaunchDarkly administrative dashboard.In this particular demo, I'm using the "private_attribute_names" option to define private fields in the LaunchDarkly client configuration. I could have also used the "privateAttributeNames" property of the user object to omit fields on per-evaluation basis.

If we start running this node.js script, we can see that our user gets reported in the LaunchDarkly administrative dashboard:[![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-private-user-data.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-private-user-data.png)

As you can see, LaunchDarkly lets us know that the "email" address was provided during feature flag evaluation on the client; but, that it was marked "private" and was not actually sent to the LaunchDarkly user database.

Now, even though LaunchDarkly doesn't know what the email address is, we can create targeting rules that evaluate against the private data. In this case, I'm going to create a rule that targets any email address ending with "@bennadel.com":[![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-private-field-targeting.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-private-field-targeting.png)

Right now, the Targeting for this feature flag is turned off. However, if we run our node.js script, then turn this feature flag's Target on, we can see the runtime evaluation of the feature flag change in our terminal:

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-private-field-evaluation-on-client.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/03/launchdarkly-private-field-evaluation-on-client.png)How cool is that! You can't tell from the screenshot but, the time it takes for the feature flag targeting rules to synchronize with my local development environment is near instant. Check out the video to see how this works in realtime.

When we started using LaunchDarkly, the feature set was simple: you provide user identifiers and then target those identifiers in the administrative dashboard. In the past few years, LaunchDarkly has added a number of exciting feature that I haven't yet taken the time to explore. But, the ability to define some user properties as "private" is just awesome.


*  *  *


_Ben Nadel (@BenNadel) is the "Co-founder of @InVisionApp, Inc. I live and breathe #JavaScript, #NodeJS, #AngularJS, #ColdFusion, and #UserExperience."_

















