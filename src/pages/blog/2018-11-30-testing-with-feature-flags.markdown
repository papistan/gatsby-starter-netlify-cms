---
author: levlaz
comments: false
date: 2018-11-30 20:38:52+00:00
layout: post
link: https://launchdarkly.com/blog/testing-with-feature-flags/
slug: testing-with-feature-flags
title: Strategies for Testing with Feature Flags
wordpress_id: 193564
categories:
- Feature Management
tags:
- end to end testing
- feature flags
- feature management
- integration testing
- QA
- quality assurance
- testing
- UAT
- unit testing
- user acceptance testing
---

Feature flag driven development empowers development teams to deliver value to customers at a much faster pace with a lot less risk. But at the same time it also creates additional complexity when it comes to testing. In this post we will discuss some of the challenges with testing in a world of feature flags, and provide some recommendations for how to address these challenges.

To help frame the discussion, we will define 5 types of tests that might exist in your testing strategy:



 	
  1. **Unit Tests:**Testing individual functions.

 	
  2. **Integration Tests****:** Testing the combination of various functions or modules.

 	
  3. **End to End Tests****:** Sometimes referred to as functional tests, testing actual user flows through your application.

 	
  4. **Quality Assurance (QA) Testing:** Testing to verify that the functionality meets requirements.

 	
  5. **User Acceptance Testing (UAT):** Testing to receive validation from stakeholders that the functionality meets requirements.


The first three test types are typically automated and executed as a part of the Continuous Integration (CI) process. QA testing can be a combination of manual and automated tests, and is sometimes performed by a dedicated QA team. The first four test types help to answer the question of “did you build the thing right”, whereas UAT helps to answer the question of “did you build the right thing?”


### Unit Testing


Unit testing is the simplest part of this puzzle. Since unit tests are supposed to test out individual pieces of functionality, wrapping that functionality in feature flags should not matter in the context of a unit test. You should continue to write unit tests as usual for all pieces of code in your application and test them independently.

To illustrate this, consider the following pseudocode:

    
    // Functions
    function newSearch(searchTerm) {
        result = MySQL.getall(searchTerm);
        return result;
    }
     
    function oldSearch(searchTerm) {
        result = ElasticSearch.getall(searchTerm);
        return result;
    }
     
    // Feature Flag
    useNewSearch = ldclient.variation("new-search-algorithm", user, false);
     
    if (useNewSearch) {
        newSearch(searchTerm);
    } else {
        oldSearch(searchTerm);
    }
     
    // Unit Tests
    function testNewSearch(searchTerm) {
        result = newSearch(searchTerm);
     
        assert(result.contains(searchTerm));
    }
     
    function testOldSearch(searchTerm) {
        result = oldSearch(searchTerm);
     
        assert(result.contains(searchTerm));
    }


In this example, we are introducing a new search algorithm that uses either MySQL or ElasticSearch to get the results. Our feature flag determines which search algorithm to use. At the unit test level, notice that we write two tests that have nothing to do with the feature flag. These tests assert that our underlying search algorithm is working properly regardless of which external method calls the search function.


### Integration Testing


Things start to get a bit more complex when it comes to integration testing and end to end testing. In these types of tests you are testing multiple pieces of code working with each other. Feature flags begin to matter here because the current state of a flag could violate the assertions that you are creating in your tests.

At first, the solution to this problem seems to be to write a test case for each variation of a feature. This approach work very well when you have a small number of flags. However, as soon as you get more than a couple of flags you begin to experience what is known as a [combinatorial explosion](https://en.wikipedia.org/wiki/Combinatorial_explosion).

If you have one boolean feature flag you can easily write a test case for the “on” and “off” state. If you have three boolean feature flags, things become a bit more complex since you need to write 8 test cases for each possible combination. In practice, most of our users have dozens if not hundreds of feature flags. In addition, the variations are not simply boolean but can have an unbounded number of variations utilizing multivariate feature flags.

As the diagram below shows, this quickly becomes a major problem. For example if you have 10 boolean feature flags you need to write 1024 test cases to test each possible combination. If you have 10 multivariate feature flags with 4 variations each, you would have to write over a million test cases to test each unique combination.

[![Number of Combinations](https://blog.launchdarkly.com/wp-content/uploads/2018/11/Number-of-Combinations.png)](https://blog.launchdarkly.com/wp-content/uploads/2018/11/Number-of-Combinations.png)

This is clearly untenable. Even if you found some sane way to automate the creation of these test cases, the amount of time that you would spend running your entire test suite would quickly start to outweigh any benefit that you are getting from feature flagging in the first place.

The same problem applies to QA and UAT testing. Most QA and UAT testers would prefer not to have a list of one million combinations to work through.


### Testing Strategies for Automated Tests


As we have seen, it can be very challenging to do traditional automated integration testing with feature flags. We would not recommend attempting to handle every possible case. Instead, a couple of strategies are outlined below:



 	
  * ******Keep writing unit tests, nothing changes here.******

 	
  * **Test for the disaster scenario.
**When you implement the LaunchDarkly SDK you are required to add a hard coded fallback value. This defines which variation of a feature to serve in the event that for whatever reason we are not able to evaluate this flag. Testing against the “offline” state of LaunchDarkly is a great way to ensure that your users will continue to have a sane experience even if all of your feature flags are in their default state. You can achieve this by starting the SDK in “offline” mode.

 	
  * **Test the current production state.**
Similarly, running your integration tests against the current production state will provide you with some confidence that once you deploy into production, everything will more or less still work. You can achieve this by pointing the SDK to your production environment when it initializes, or mock the requests by pulling down the current production state via our API.

 	
  * **Test some personas.**
If your feature flag rules take advantage of user targeting, it might be useful to create some testing personas that you use in your end to end tests. You can achieve this by ensuring that your user object contains valid attributes that will be evaluated by the LaunchDarkly SDK.

 	
  * **Test combinations, sometimes.**
There may be times when you have a critical feature with many variations that must be tested. You should be selective when writing tests that view all possible combinations. This approach should be used sparingly, and you should never test all combinations of all possible feature flags.




### Testing in Production


We talk a lot about [testing in production](https://www.meetup.com/Test-in-Production/). Testing in production does not mean shipping code with no tests into production and hoping for the best. Instead, it means having the ability to have real users test real features, with real data, in a real environment.

Some of our most successful users are able to deploy to production multiple times per day because they have empowered their QA and UAT teams to validate functionality in a real production environment before exposing it to the rest of their use base. When QA or UAT reveals a flaw, there is no impact on anyone other users and there is no need to do a full rollback.

This is the real power of feature flags. You will never be able to find every bug in your software no matter how much automated testing you do. But having the ability to turn a feature off when you find a bug in production in real time is what gives our customers the peace of mind to be able to continue to deliver features to customers safely and as fast as possible.
