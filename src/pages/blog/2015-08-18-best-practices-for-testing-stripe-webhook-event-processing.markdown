---
author: patrickkaeding
comments: false
date: 2015-08-18 01:25:06+00:00
layout: post
link: https://launchdarkly.com/blog/best-practices-for-testing-stripe-webhook-event-processing/
slug: best-practices-for-testing-stripe-webhook-event-processing
title: Best practices for testing Stripe webhook event processing
wordpress_id: 122
categories:
- Feature Management
tags:
- Mailchimp
- NewRelic
- SendWithUs
- stripe
- webhook event processing
- webhooks
---

While writing the code to integrate our application with [Stripe](https://www.stripe.com), I was very impressed with the level of polish that Stripe has put on their API, in the documentation, the language-specific SDK ergonomics, and how easy they make it to integrate with some so obviously complex as payment processing.

However, there were two areas in which things were not great in the development/testing process, both surrounding webhooks:



 	
  * Testing webhook processing

 	
  * Webhooks from one test environment being sent to another environment




## Handling webhooks from Stripe


Stripe can be configured to send events to your application via webhooks. In this way, you can maintain the internal state of your customers as they transition through the payment process. However, there is no way to know that the webhook request actually came from Stripe.

In order to verify the authenticity of the webhook payload, we need to fetch the event from Stripe's API, ignoring the payload from the webhook (except the event ID, which we use to perform the lookup). Since we initiate the call to Stripe's API, and it is secured over HTTPS, we can trust that we are getting accurate data from Stripe. Once we have a valid event, we can do whatever processing we need to on it. This is the process suggested by Stripe:


<blockquote>_If security is a concern, or if it's important to confirm that Stripe sent the webhook, you should only use the ID sent in your webhook and should request the remaining details from the API directly. We also advise you to guard against replay-attacks by recording which events you receive, and never processing events twice._</blockquote>


(I hope all of Stripe's customers would consider security to be 'a concern', since we are dealing with payment processing.) The second note about avoiding replay attacks is also worth noting, but it is relatively easy to take care of— just record each webhook payload in a database collection with a unique index, and check if the insert succeeded before proceeding.


## Testing webhooks from Stripe


The problem with this approach for validating webhook data is that it makes integration testing difficult, because Stripe doesn't send invoice webhook events right away:


<blockquote>_If you have configured webhooks, the invoice will wait until one hour after the last webhook is successfully sent (or the last webhook times out after failing)._</blockquote>


So, imagine a test script that does the following:



 	
  * Sign up a user with a new plan

 	
  * Update the user's credit card to be one that will fail to charge (4000000000000341 is the test card number that Stripe provides for this purpose)

 	
  * Change the trial end date to end in one second (other tests will ensure that the trial period works properly, but this is meant to test the renewal flow)

 	
  * Wait 5 seconds, to be sure the trial has ended, and the webhook has been sent

 	
  * Ensure that the account is put into the 'charge failed' mode


However, the 'Wait 5 seconds' step isn't right, since we might need to wait up to an hour. This is way too long to wait to know if our tests pass. So, what else can we do? We can't just fake the webhook event, since our code needs to fetch the event from Stripe to be sure it is authentic.


### Disable authenticity check in test mode


The solution we settled on was to disable the authenticity check in test mode. Since testing just that we can fetch an event from Stripe isn't a terribly interesting test (and presumably, it is covered by their SDK test suite), I'm comfortable with this deviation between the test and production flows. In the end, the test script listed above looks more like this (the test app has the 'test mode' flag enabled, which disables the event fetching):



 	
  * Sign up a user with a new plan

 	
  * Update the user's credit card to be one that will fail to charge (4000000000000341 is the test card number that Stripe provides for this purpose)

 	
  * Change the trial end date to end in one second (other tests will ensure that the trial period works properly, but this is meant to test the renewal flow)

 	
  * **Send a fake webhook event that looks like one Stripe would send for a failed invoice charge** (be sure to use a unique event ID, so that it won't trigger the replay attack detection code— test that code in a different test)

 	
  * Ensure that the account is put into the 'charge failed' mode




### How could this system be improved?


If I were to implement a webhook-sending service, I would include a header on the request including an [HMAC](http://en.wikipedia.org/wiki/HMAC) value that could be used to verify that the request was coming from a trusted origin. The HMAC process is detailed in [RFC 2104](https://www.ietf.org/rfc/rfc2104.txt), but it can be summarized as:

1. The sender prepares the message to be send (the webhook payload, in this case).
2. The sender computes a signature using the message payload and a shared secret (this could be the Stripe secret key, or it could be separate secret used only for this purpose, as long as it is known to both Stripe and your application, and no one else).
3. The sender then sends the message along with the signature (usually in an HTTP header).
4. The receiver (ie, your application) takes the message and computes its own HMAC signature, using the shared secret.
5. The receiver compares the signature it computed with the one that was received, and if they match, the message is authentic.


## Avoiding webhook confusion


The next problem we faced was dealing with renewal webhooks being sent to our staging server, referencing unknown accounts. The problem can be summarized like this:



 	
  * Stripe only supports two modes: Live and Test

 	
  * We have many non-production systems: staging, dogfood, each developer's local instance, etc

 	
  * Webhooks are retried by Stripe until they succeed. If you have multiple webhooks configured, each one will be retried until it succeeds (so if you have three configured, and one succeeds while the others fail, the others will be retried).

 	
  * In production, a failing webhook would be a problem that would require investigation—we don't want something like that to fail silently.


So, if I am testing/developing the signup flow on my laptop, and my local app is configured with the 'Test' Stripe credentials, webhooks resulting from these interactions will be sent to our Staging server (since we have webhooks in the 'Test' mode configured to go there).

Staging will get the webhook payload, validate it, and then look at the account ID to do its work. Then, it will find that it doesn't know about the referenced account, log an error message, and return a non-successful status to Stripe, indicating that it should retry. This is the desired workflow in production if processing a webhook fails in this way.

So, how do we avoid this noise in our alerting system? We don't want to disregard all errors in staging; how would we catch issues before they get to production?

The answer we settled on is simple, but it still feels a little hacky: sign up for a second Stripe account. Don't use the 'Live' mode in this account, and don't configure any real bank info. Don't keep any webhooks configured in there (but for testing ad hoc issues, you can add one, possibly using an [ngrok](https://ngrok.com/) url pointing to your local instance). Use this new dummy account for local developer configs, and use the real account's 'Test' mode for staging.


## How could this be better?


Considering how Stripe really covers all the bases in other areas, and provides an amazingly easy to use and powerful system, it is kind of surprising that they don't have better support for customers who also have even moderately complex testing requirements. We recently implemented our own [support for different environments](http://launchdarkly.com/blog/feature-flag-environments/), so we did some research into how other services solve this problem:



 	
  * [SendWithUs](https://www.sendwithus.com/) - they differentiate between production and non-production, but they allow you to create many non-production API keys, that behave differently. So my local test key can have all emails sent to my email (regardless of the original recipient), and Alexis's key can have emails sent from his laptop go to his email, while John's key can not send any real emails at all. All of these test emails will end up in the same bucket of 'test' emails in the logs on the SendWithUs console (so they aren't siloed all the way through), but the analytics are not tracked on test emails, so they don't interfere with your production metrics. All test & production keys can share the same templates, drip campaigns, etc. You can create as many keys as you like. I think this scheme works well for SendWithUs's product, but it wouldn't likely work for other products that need environments' data to remain fully siloed.

 	
  * [NewRelic](http://newrelic.com/) - You can create different 'applications' for each environment, and they remain fully siloed. There is no different between the same codebase running in production vs. staging and a completely different application.

 	
  * [Mailchimp](http://mailchimp.com/) - You can create different lists, and have staging subscribe people to the staging list, while production subscribes people to the production list. This is very similar to the NewRelic approach, but in a different domain.

 	
  * LaunchDarkly - This blog post isn't meant to go into depth about our environments feature, there are [other](http://launchdarkly.com/blog/feature-flag-environments/) [places](http://docs.launchdarkly.com/docs/environments) for that. But, we did something more like SendWithUs, where the environments can share common data, like goals or the basic existence of features, but allows you to have different rules for each environment, and keeps all data siloed.


So, that is how a few other companies have solved this problem, how could Stripe improve their solution? My first suggestion is to allow me to create as many environments as I need, and keep all data siloed. Alternatively, they could allow me to create groups of webhooks, such that only one in each group must succeed before considering it delivered. This would solve my problem right now, but it feels less flexible than multiple environments, and would likely not solve other people's problems.



* * *





###### _LAUNCHDARKLY HELPS YOU BUILD BETTER SOFTWARE FASTER WITH FEATURE FLAGS AS A SERVICE. START YOUR FREE TRIAL [NOW](https://app.launchdarkly.com/signup#/?utm_source=launchdarkly_blog&utm_medium=organic)._



