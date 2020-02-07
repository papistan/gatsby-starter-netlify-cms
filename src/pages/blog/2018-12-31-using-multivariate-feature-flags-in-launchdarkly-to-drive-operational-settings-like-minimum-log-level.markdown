---
author: Guest
comments: false
date: 2018-12-31 22:35:41+00:00
layout: post
link: https://launchdarkly.com/blog/using-multivariate-feature-flags-in-launchdarkly-to-drive-operational-settings-like-minimum-log-level/
slug: using-multivariate-feature-flags-in-launchdarkly-to-drive-operational-settings-like-minimum-log-level
title: Using Multivariate Feature Flags In LaunchDarkly To Drive Operational Settings
  Like Minimum Log Level
wordpress_id: 193658
categories:
- Feature Management
tags:
- feature flag
- feature management
- javascript
- multivariate
---

_Originally published [here](https://www.bennadel.com/blog/3426-using-multivariate-feature-flags-in-launchdarkly-to-drive-operational-settings-like-minimum-log-level.htm) by Ben Nadel on March 23, 2018._

After having used LaunchDarkly as our feature flag service provider for several years, I'm taking a fresh look at their documentation in order to see what new hawtness they offer above and beyond the traditional On / Off toggle. Yesterday, I looked at [LaunchDarkly's ability to target users based on Personally Identifiable Information (PII)](https://www.bennadel.com/blog/3425-using-launchdarkly-to-target-personally-identifiable-information-pii-during-feature-flag-evaluation-without-leaking-sensitive-data.htm) without having to actually send said PII to the LaunchDarkly servers. This morning, I wanted to take a look at their new "multivariate" feature flags. Rather than just a Boolean setting, these feature flags allow engineers to define custom settings. So, rather than a simple Boolean, a multivariate feature flag could be a list of different strings, numbers, or Booleans. To explore this concept, I wanted to define an Operations feature flag that would allow me to change the minimum log-level being used by a given application.

[embed]https://vimeo.com/261473231[/embed]

By default, all of the LaunchDarkly feature flags are Booleans. Which means that they result in either a "true" or "false" value. A "multivariate" feature flag can also provide a "true" / "false" dichotomy. But, it can also provide an arbitrary set of string values. Or number values. Or some combination of the three. So, if we want to create a long-lived Operations feature flag to drive log-level in our application, we can create a multivariate flag in which each option defines the minimum log-level as a string value:

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/12/launchdarkly-multivariate-feature-flags-log-level.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/12/launchdarkly-multivariate-feature-flags-log-level.png)

As you can see, this feature flag, "operations-minimum-log-level", defines the following string variations:



 	
  * error

 	
  * warn

 	
  * info

 	
  * debug


With this flag in place, I get then enable targeting that delivers one of these four string values:

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/12/launchdarkly-multivariate-targeting.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/12/launchdarkly-multivariate-targeting.png)

Now that we have our multivariate feature flag defined, let's look at how we can use it in the code. Like yesterday, I've created a simple node.js loop that executes once every second. This time, however, the loop is going to be consuming an instance of our Logger service. The Logger service will expose traditional logging methods like .error(), .warn(), and .info(). However, internally, the service will examine our "operations-minimum-log-level" feature flag to see which, if any, of the logging requests should be ignored.

    
    // Require the core node modules.
    var chalk = require( "chalk" );
    var config = require( "./config" );
    var LaunchDarkly = require( "ldclient-node" );
     
    // ----------------------------------------------------------------------------------- //
    // ----------------------------------------------------------------------------------- //
     
    // I log messages to the console.
    // --
    // NOTE: I limit the log output based on the current operational feature flag settings.
    class Logger {
     
    	constructor ( ldClient ) {
     
    		this.ldClient = ldClient;
    		this.previousLevel = null;
     
    	}
     
    	// ---
    	// PUBLIC METHODS.
    	// ---
     
    	async debug ( message ) {
     
    		if ( await this._canLog( "debug" ) ) {
     
    			console.log( chalk.grey( chalk.bold( "DEBUG:" ), message ) );
     
    		}
     
    	}
     
    	async error ( message ) {
     
    		if ( await this._canLog( "error" ) ) {
     
    			console.log( chalk.red( chalk.bold( "ERROR:" ), message ) );
     
    		}
     
    	}
     
    	async info ( message ) {
     
    		if ( await this._canLog( "info" ) ) {
     
    			console.log( chalk.cyan( chalk.bold( "INFO:" ), message ) );
     
    		}
     
    	}
     
    	async warn ( message ) {
     
    		if ( await this._canLog( "warn" ) ) {
     
    			console.log( chalk.magenta( chalk.bold( "WARN:" ), message ) );
     
    		}
     
    	}
     
    	// ---
    	// PRIVATE METHODS.
    	// ---
     
    	async _canLog( level ) {
     
    		// Get the minimum log-level from the given LaunchDarkly client. Since this is
    		// an OPERATIONAL flag, not a USER flag, the "key" needs to indicate the current
    		// application context. In this case, I'm calling the app, "node-test-app". If I
    		// wanted to get more granular, I could use something like machine ID. But, for
    		// this particular setting, I think app-name makes sense.
    		var minLogLevel = await this.ldClient.variation(
    			"operations-minimum-log-level",
    			{
    				key: "node-test-app"
    			},
    			"warn" // Default / fall-back value if LaunchDarkly unavailable.
    		);
     
    		// To make the demo more interesting, let's log every time the feature flag
    		// changes in absolute value.
    		if ( minLogLevel !== this.previousLevel ) {
     
    			console.log( chalk.bgGreen.bold.white( `Switching to log-level: ${ minLogLevel }` ) );
     
    		}
     
    		// Given the minimum log level, determine if the level in question can be logged.
    		switch ( this.previousLevel = minLogLevel ) {
    			case "error":
    				return( level === "error" );
    			break;
    			case "warn":
    				return(
    					( level === "error" ) ||
    					( level === "warn" )
    				);
    			break;
    			case "info":
    				return(
    					( level === "error" ) ||
    					( level === "warn" ) ||
    					( level === "info" )
    				);
    			break;
    			default:
    				return( true );
    			break;
    		}
     
    	}
     
    }
     
    // ----------------------------------------------------------------------------------- //
    // ----------------------------------------------------------------------------------- //
     
    // NOTE: Internally, the LaunchDarkly client will set up an INTERVAL, which will hold
    // the node.js process open until you explicitly .close() the client. In a long-running
    // application, this doesn't matter. But, in a "test" script, just something be aware of.
    var launchDarklyClient = LaunchDarkly.init( config.launchDarkly.apiKey );
     
    // Create a new instance of our logger that will use the given LaunchDarkly client in
    // order to determine which level of logging to allow.
    var logger = new Logger( launchDarklyClient );
    var loop = 0;
     
    launchDarklyClient.waitUntilReady().then(
    	function executeLoop () {
     
    		// NOTE: This is for the demo's visual feedback, not for actual logging.
    		console.log( chalk.dim.italic( `Loop ${ ++loop }` ) );
     
    		// In each loop execution, we're going to log messages at different severity
    		// levels. Since we don't want to scatter log-level logic throughout the app,
    		// we're going to encapsulate the minimum log-level check inside our logging
    		// service. This way, the rest of the app can log as it sees fit and not have
    		// to worry about operational settings.
     
    		logger.debug( "Executing loop." );
     
    		try {
     
    			logger.debug( "Checking free memory." );
    			var memoryUsed = readMemory();
    			logger.info( `Memory used: ${ memoryUsed }%` );
     
    			if ( memoryUsed >= 50 ) {
     
    				logger.warn( "More than half of free memory has been allocated." );
     
    			}
     
    		} catch ( error ) {
     
    			logger.error( `Memory could not be read: ${ error.message }` );
    		}
     
    		setTimeout( executeLoop, 1000 );
     
    	}
    );
     
    // ----------------------------------------------------------------------------------- //
    // ----------------------------------------------------------------------------------- //
     
    // I provide a fake memory input, randomized to throw errors.
    function readMemory() {
     
    	var memory = ( Math.random() * 100 ).toFixed( 1 );
     
    	if ( memory <= 30 ) {
     
    		throw( new Error( "IOError" ) );
     
    	}
     
    	return( memory );
     
    }


As you can see, we're using various log-level statements to trace the control-flow through the application. We're also using some randomness to throw errors such that we can exercise all of the available log-levels.

Now, if we start the node.js process in "debug" mode and then switch our multivariate feature flag over to "warn" mode, we get the following terminal output:

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/12/launchdarkly-multivariate-feature-flags-demo.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/12/launchdarkly-multivariate-feature-flags-demo.png)

As you can see, when we start our operations feature flag, "operations-minimum-log-level", in "Debug" mode, our Logger service outputs all of the log messages. However, when we switch the feature flag over to "warn" mode, our Logger service only outputs "error" and "warn" messages. And, like yesterday, if you watch the video, you can see just how fast LaunchDarkly syncs the rules database in the background.

Historically, I've been using feature flags to safely rollout new features, with the intent of removing the feature flag once the new feature has been "proven." With multivariate feature flags, however, the concept of a long-term feature flag starts to become a lot more powerful. Now, we can really use LaunchDarkly to help drive actual site operations.

Of course, we can certainly have long term Boolean variations. However, allowing for arbitrary string value variations really opens up new possibilities. In fact, just yesterday, [Ted Pennings](http://ted.pennin.gs/) - one of my co-workers at [InVision](https://www.bennadel.com/invision/co-founder.htm?redirect=https%3A%2F%2Fwww%2Einvisionapp%2Ecom%2F%3Fsource%3Dbennadel%2Ecom) - mentioned using custom variations to drive site-status messaging:

[![](https://blog.launchdarkly.com/wp-content/uploads/2018/12/ted-pennings-launchdarkly-variations.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/12/ted-pennings-launchdarkly-variations.png)

What a great idea! It's exciting to see LaunchDarkly really maturing their product. There's lot of feature flag goodness to start using.


*  *  *


_Ben Nadel (@BenNadel) is the "Co-founder of @InVisionApp, Inc. I live and breathe #JavaScript, #NodeJS, #AngularJS, #ColdFusion, and #UserExperience."_
