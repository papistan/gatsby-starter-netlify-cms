---
author: justinucd
comments: false
date: 2017-03-01 17:00:34+00:00
layout: post
link: https://launchdarkly.com/blog/implementing-feature-flags-in-an-angular-e-commerce-app/
slug: implementing-feature-flags-in-an-angular-e-commerce-app
title: Implementing Feature Flags in an Angular E-commerce App
wordpress_id: 1429
categories:
- Feature Management
tags:
- Angular
- feature flags
- single page apps
- spas
---

E-commerce applications can take on many forms. Whether they’re retail, goods exchange, or an auction website, online commerce is becoming more common than offline. Modern front-end frameworks, such as Angular and React, provide the tools necessary for creating fast and responsive single-page e-commerce apps. In this article, we’ll delve into the process of using the [LaunchDarkly JavaScript SDK](https://github.com/launchdarkly/js-client) to introduce new functionality in an AngularJS e-commerce application.

**E-Commerce + Real-Time Feature Flags**

With the growing demand for quicker, more reliable releases, development teams should consider having feature toggles in their toolbox. The user-facing nature of web stores facilitates the perfect environment in which feature flagging promotes granular control and feature visibility.  Some of the use cases include:



 	
  * Rolling out storewide discounts with minimal overhead

 	
  * Gradually rolling out new checkout and payment systems and assessing performance and revenue impact before fully rolling out

 	
  * Allowing customers to personalize their shopping experience

 	
  * Serve promotions and recommend items based on a customer’s preferences and previous behavior


Having these implementations wrapped in feature flags creates a safety net for catching even the smallest discrepancies, such as outdated seasonal discounts and conflicting pricing rules.

**Using Feature Flags in an E-commerce Environment**

Feature flags prove to be incredibly valuable in an online store. In such a fast-paced environment, product pricing is constantly changing, with various discounts and markdowns being put into effect. We’ve created an open-source Angular application (based on Code Project’s [ShoppingCart](https://www.codeproject.com/Articles/576246/A-Shopping-Cart-Application-Built-with-AngularJS)) demonstrating the power of feature flagging in an e-commerce application. In our app, we implement a multivariate feature flag named “store-discount” which returns a number indicating a percentage discount on all products.

**Integrating**

To integrate LaunchDarkly feature flags with our Angular app, we will need to begin by creating a service which will initialize the LaunchDarkly client. Using Angular’s [$q](https://docs.angularjs.org/api/ng/service/$q) dependency allows us to return a promise which will resolve when the client has prepared its initial set of feature flags.

    
    storeApp.factory('LaunchDarklyService', ['$q', '$rootScope', function($q, $rootScope) {
      var initLD = function () {
        var deferred = $q.defer();
        var ldclient = LDClient.initialize(
          'YOUR-ENVIRONMENT-KEY', 
          {key:'test', anonymous:true})
        ldclient.on('ready', function () {
          deferred.resolve(ldclient)
        })
        return deferred.promise
      }
      return {initLD: initLD }
    }])
    


Now, our main controller can use our newly defined LaunchDarklyService to initialize the feature flag client, and save it in the application’s root scope (a set of data available to any page in our app) once the client is ready.

    
    function storeController($scope, $rootScope, $routeParams, DataService, LaunchDarklyService, ngDialog) {
      ...
      // initialize the LaunchDarkly client  
      if ($rootScope.ldclient === undefined) {
        LaunchDarklyService.initLD().then(ldclient => {
          $rootScope.ldclient = ldclient
          $scope.discount = $rootScope.ldclient.variation('store-discount')
          // listen for changes in the store-discount feature flag, and update the discount accordingly
          $rootScope.ldclient.on('change', function () {
            ngDialog.open({
              template: 'modal.html',
              className: 'ngdialog-theme-default',
              scope: $scope
            })
            $scope.discount = $rootScope.ldclient.variation('store-discount')
            $scope.$apply()
          })
        })
      } else {
        $scope.discount = $rootScope.ldclient.variation('store-discount')
      }
      ...
    }


Also, the controller starts a listener within the LaunchDarkly client to change the current value of the store’s universal discount whenever a flag is modified. This allows the app to dynamically render new information. In our case, prices are slashed, and a notification pops up, alerting the user of “amazing new discounts!” This is achieved by using an ngIf directive to slash through the original price, if a discount has been applied.

    
    <tr ng-repeat="product in store.products | orderBy:'name' | filter:search" >
      ...
      <td class="tdRight">
        <strike ng-if="$parent.discount > 0">{{product.price | currency}}  </strike> {{product.price-product.price*discount | currency}}
      </td>
      ...
    </tr>


Here is a video showcasing our completed multivariate flag in action:

[video width="2548" height="1330" mp4="https://blog.launchdarkly.com/wp-content/uploads/2017/02/angular-store-demo.mp4"][/video]

**Try it out**

This demo was built on top of Code Project’s [ShoppingCart](https://www.codeproject.com/Articles/576246/A-Shopping-Cart-Application-Built-with-AngularJS), and the code is available for your use on [GitHub](https://github.com/launchdarkly/angular-shopping-flags). You can checkout the JavaScript SDK functionality [here](http://docs.launchdarkly.com/docs/js-sdk-reference).

—-

_**Primary Contributor:  **[Arnold Trakhtenberg](https://github.com/atrakh/), Engineering Content Consultant at LaunchDarkly_
