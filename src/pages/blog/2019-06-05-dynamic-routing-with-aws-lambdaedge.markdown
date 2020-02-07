---
author: Guest
comments: false
date: 2019-06-05 15:35:30+00:00
layout: post
link: https://launchdarkly.com/blog/dynamic-routing-with-aws-lambdaedge/
slug: dynamic-routing-with-aws-lambdaedge
title: Dynamic Routing with AWS Lambda@Edge
wordpress_id: 193970
categories:
- DevOps
- Feature Management
tags:
- AWS
- DynamoDB
- feature flags
- Lambda
- routing
---

_Originally published by on [TrueCar's blog, Driven by Code](https://medium.com/driven-by-code/dynamic-routing-with-aws-lambda-edge-4537c7d5b2b8), on April 11th, 2019._

[TrueCar](https://www.truecar.com/) is a digital automotive marketplace that provides comprehensive pricing transparency about what other people paid for their cars and enables consumers to engage with TrueCar Certified Dealers who are committed to providing a superior purchase experience. TrueCar operates its own branded site and a nationwide network of more than 15,000 Certified Dealers. TrueCar also powers car-buying programs for several hundred U.S. membership and service organizations, including USAA, AARP, American Express, AAA, and Sam’s Club. Including traffic to these “partner” sites and to TrueCar’s branded site, over one half of all new car buyers engage with the TrueCar network when they purchase a car.

TrueCar had been hosting its internet presence in one or more colocation facilities with traditional business, design, development, and operational staff working to produce a world-class website experience for consumers. Early in 2016, TrueCar decided to move internet operations off premises from its data centers to the AWS cloud. Many of TrueCar’s legacy codebases and features had grown organically over the previous ten years, and some of these were getting long in the tooth. New features were difficult to roll out and existing features were difficult to change. Deployments were time consuming and sometimes manual. It became clear that a move to the cloud would help speed up delivery and improve quality by creating more flexibility and allowing TrueCar to start over in many ways.

Some operational and logistical challenges were presented when TrueCar decided to move its internet infrastructure into the AWS cloud. Moving domain names in the past had involved changing DNS entries one at a time, or using “wildcard” entries. To update domain names manually as part of the move to AWS would have been a painstaking and lengthy process, with over 500 partner domains to potentially touch. Not only did TrueCar need to move their domain DNS entries, they also needed to revamp their entire architecture, software, and operational practices. TrueCar had also adopted the Site Reliability Engineering model of Devops, which requires business owners, software engineers, and operational engineering to work together as a single team to deliver the best automotive marketplace platform on the internet.

To complicate issues, the legacy codebase and architecture had to remain in place while TrueCar built out a new platform for the transition. As a result, they needed a way to develop, test, and roll out customer experiences for each partner site and application with minimal disruption, to avoid lengthy delays or tying up the business for long periods of time during the transition.


### Challenges





 	
  * TrueCar needed to move hundreds of partner sites

 	
  * Each partner is important, but some are quite large and have a larger impact on the business

 	
  * TrueCar needed to selectively switch traffic and applications between the legacy and new platforms

 	
  * Rollouts were slow, sometimes manual, and required DevOPs involvement

 	
  * Updating DNS entries was slow and cumbersome, making the entries difficult to maintain and shift

 	
  * DNS entries were not granular enough to apply to portions of traffic or applications

 	
  * CloudFront routing rules were constrained by the number of behaviors and having to manage behaviors to be consistent across distributions

 	
  * Pure infrastructure changes, like CloudFront and DNS, were usually opaque to business owners and software engineers




### Solution


The solution that we devised emerged after the Amazon Web Services (AWS) launched [Lambda@Edge](https://aws.amazon.com/lambda/edge/) in mid-2017. We had already been using the powerful Lambda platform for certain infrastructure tasks and heavy lifting in AWS. This experience made us feel confident that we could use the power of Lambda and the power of software code to dynamically route traffic for our partners and applications. We decided to use a rules engine based in [DynamoDB](https://aws.amazon.com/dynamodb/), and utilizing Lambda@Edge in [CloudFront](https://aws.amazon.com/cloudfront/) requests to programmatically switch traffic as needed. This would give us a scalable, flexible, easy, and fast method for setting up routing rules and modifying traffic flows in near real-time. Here’s a well-known diagram of the request flow in CloudFront:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-1.jpeg)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-1.jpeg)

Below is an adaptation of this diagram that shows how TrueCar routes traffic by using a rules lookup.

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-2.jpeg)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-2.jpeg)


### Implementation




#### DynamoDB


We started by creating a table in DynamoDB for which the hash key is equal to the HOST part of the request. In many cases, the host is [www.TrueCar.com,](http://www.truecar.com%2C/)but it can also be a partner site. We also included a range key for the URI part of the request. The URI is the path to the application that the user is accessing. Including both the host and URI provides a distinct ruleset for each HOST:URI combination that Lambda@Edge encounters, as well as to search for any rules that match just the HOST.

Here’s an example of a rule engine in JSON that’s been mapped to DynamoDB:

    
    Promise.all([exactMatch, partialURIMatch, defaultURIMatch])
        .then(actionlist => {
          actionlist.forEach(actions => {
            if (actions.length > 0) {
              action = weightedRandomChoice(actions);
              return executeAction(action, request, response);
    …
        .then(function(map) {
          if (map) {
            if (map.response) {
              console.log('New response', map.response);
              callback(null, map.response);
            } else {
              console.log('New request', map.request);
              console.log('New headers', map.request.headers);
              callback(null, map.request);
            }


In this example, you can see that there can be two rules of equal weight, meaning that half our traffic would see index.html and half would see index2.html. In each rule, you can also see that there are certain actions that we could change, like setHeaders and setOrigin. This is where the power of the rules engine is clear. Using rules, we can dynamically switch the origin that CloudFront accesses when it serves our traffic, sending some traffic to our legacy datacenter and some to our new platform in AWS.


#### Lambda@Edge NodeJS goodness


To enable the switching, we wrote code for Lambda@Edge uses to match rules and implement the solution. First, we made several DynamoDB calls asynchronously with NodeJS’s fast architecture, which return either a modified result or a direct response. Each match routine is an asynchronous promise that returns a hierarchy of matches: an exact match on the host and URI, a partial match on the URI, and a default as a fall back. We check each of these matches in order, and then execute the corresponding action. Based on the results of the first match in the section, we could send back a direct synthetic response or reroute the request to a new origin.

The following JSON code illustrates the different actions or rules that we can execute, depending on the match, using a switch statement to specify an operation to perform — like setURI, setHeaders, or setOrigin. We also include a deep string scan and replace function to let us use templates in the JSON rulesets so that we could customize the returned strings with rich information from the headers, the request path, or other information we had available.

    
    function executeAction(action, request, response) {
      console.log('got action', action);
      // first pass is for requests
      Object.keys(action).forEach(key => {
        switch (key) {
          case 'setURI':
            console.log('Update URI', action[key]);
            request.uri = _deep_string_scan_replace(action[key]);
            break;
          case 'setHeaders':
            console.log('Update headers', action[key]);
            let newHeader = _deep_string_scan_replace(action[key]);
            Object.assign(request.headers, newHeader); // merge
            break;
          case 'setOrigin':
            console.log('Update origin', action[key]);
            request.origin = updateOrigin(action[key]);
            break;
          default:
            console.log('Skipping request phase key', key);
            break;
        }
      });
      // second pass is for responses
      Object.keys(action).forEach(key => {
        switch (key) {
          case 'browserRedirect':
            console.log('Redirecting the browser', action[key]);
            response = _deep_string_scan_replace(action[key]);
            break;
          default:
            console.log('Skipping response phase key', key);
            break;
        }
      });
      return {
        response: response,
        request: request,
      };
    }
    




#### Performance


We were concerned initially about a potential performance impact from Lambda@Edge and the imposed constraints of running code at the edge before our application servers could respond. TrueCar set an aggressive 100ms limit as the budget for CloudFront to process the request. In our initial testing, Lambda@Edge performed well, within a Region. Here are some performance metrics at different memory sizes:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-3-1.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-3-1.png)

As you can see, the performance of the Lambda execution decreases along with the memory size increase for the Lambda. The good news is that we hit our 100ms target at 1GB!


### Distributed Lambda@Edge in Production


By running the code in production, our CloudFront distribution could receive requests from anywhere. We were fortunate that DynamoDB Global Tables were released when we started this project. This enabled us to have the Lambda code detect the Region where it was executing, and then select the closest DynamoDB replica master as its correspondent. Here’s a diagram that illustrates the design with the DynamoDB Global Tables:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-4.jpeg)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-4.jpeg)

A quick update on this drawing that is not shown: We have since added a third region to the DynamoDB global table in us-east-2 (Ohio) to improve response times in that area.

Running this code in production, we could use Datadog to retrieve CloudWatch metrics, which let us get a sense of the application durations across each Region and whether we were executing within our 100ms budget. Keep in mind that the duration of the Lambda@Edge code directly impacts the latency that users experience with our websites, so we needed to keep these as low as possible. The following metrics demonstrate the kinds of execution times and durations that we saw:

[![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-5.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-5.png) [![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-6.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-6.png) [![](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-7.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/05/img-7.png)


### A/B Testing with LaunchDarkly


LaunchDarkly is a third party service that TrueCar uses to assign flags at runtime to turn on or off certain consumer features for A/B testing. For example, a software engineer might want to create a new website experience with larger buttons and a cleaner look. However, we may not want the changes to appear until the experience is tested and approved by a business owner. As another example, a button color might impact conversion rates or visibility on the page. So the software engineers could use a feature flag with a targeted test to see if changing the button from red, say, to green improves the consumer experience.

The LaunchDarkly framework has a NodeJS SDK integration which can be integrated with Lambda@Edge. This enables the same feature flags to be used for software engineers to A/B test user experiences and for routing in the rules engine.

The initial implementation TrueCar used to test the rules platform was to route requests to the legacy platform or the new platform by randomly generating numbers and dividing traffic up by weight. This had the benefit of being fast, but could result in a less than ideal experience if we displayed different versions of the pages on multiple page loads. During our initial rollout, it was fairly simple to serve the same (or similar enough) pages from the legacy and new platforms. As the migration expanded, however, the platforms would drift and the legacy platform might not be updated while the new platform continued to evolve and grow.

Since our software engineers were already accustomed to using LaunchDarkly with feature flags to test and roll out features and evaluate A/B responses, we thought that we could adapt that process to integrate it with Lambda@Edge for our traffic routing. As illustrated in the earlier code snippet, we used a random selection algorithm that we could easily adapt to use LaunchDarkly instead by adding an attribute key in our rules engine. The attribute key would tell the rules engine which LaunchDarkly feature flag to use, and the attribute value would tell the rules engine which flag value to match.


By adjusting the code to add a check for the ldKey attribute (which specifies which key –or feature flag– to check in LaunchDarkly), we can update the code section above to be more flexible.




    
    Promise.all([exactMatch, partialURIMatch, defaultURIMatch])
        .then(actionlist => {
          let variationPromise;
          actionlist.some(actions => {
            if (actions.length > 0) {
              if ('ldKey' in actions[0]) {
                variationPromise = ldChoice(actions, sessionUUID);
              } else {
                variationPromise = weightedRandomChoice(actions);
              }
              return true; // stop on first action
            }
          });
          return variationPromise.then(function(action) {
            return executeAction(action, request, response);
          });
        })
    


The code that implements the LaunchDarkly choice uses a variation based on the user session to return a flag which is then matched to the value we’re interested in.

With this feature enabled, business users and application software engineers can use the same A/B testing framework that they’re used to, so they can manage traffic flows across the whole infrastructure as well as within the application itself. For example, if a feature on the new platform is enabled in LaunchDarkly, then the application code displays a new page layout for the user. The same LaunchDarkly flag can be used to route the request to the correct origin where the feature is deployed. If the feature is turned off in the application, then the same feature flag can be used to route traffic back to the original endpoint.

This not only allows us to route our traffic in controllable and expected ways, but it also allows business users and application owners to participate in the infrastructure flows and rollout of new platforms.


### Summary


Using the power of Lambda and CloudFront together in the form of Lambda@Edge, TrueCar was able to execute on its plans to migrate to the cloud while providing the best experience to our site users. The introduction of A/B testing with LaunchDarkly lets software engineers, business owners, and site reliability engineers work together in a shared and agile framework to accomplish our business objectives.


*  *  *




_[Regis Wilson](https://www.linkedin.com/in/regis-wilson-a713609/) is currently a Site Reliability Engineer 5 at TrueCar. He has over 20 years of experience working as a Sr. Systems and Network Architect supporting internet businesses and developing world class infrastructure. Read more of his work on TrueCar’s blog, [Driven by Code](https://medium.com/@DrivenByCode)._
