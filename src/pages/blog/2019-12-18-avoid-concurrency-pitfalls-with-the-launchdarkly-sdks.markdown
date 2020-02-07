---
author: ebishop
comments: false
date: 2019-12-18 15:00:27+00:00
layout: post
link: https://launchdarkly.com/blog/avoid-concurrency-pitfalls-with-the-launchdarkly-sdks/
slug: avoid-concurrency-pitfalls-with-the-launchdarkly-sdks
title: Avoid Concurrency Pitfalls with the LaunchDarkly SDKs
wordpress_id: 194700
categories:
- DevOps
tags:
- . php
- .net
- C++
- concurrency
- go
- Java
- javascript
- Python
- ruby
- SDKs
- Xamarin
---

Whether writing a mobile app or a high-volume web service, developers on modern platforms often have to keep concurrency issues in mind: what happens if this process/thread/goroutine accesses a resource that this other one is using? Patterns for doing this safely are well understood, but when using a third-party library it may not always be clear where the potential issues are lurking. While the LaunchDarkly SDKs are designed for use in highly concurrent settings, there are still a few edge cases that are worth keeping in mind.

All of the following scenarios are somewhat unusual conditions that most applications won't encounter, but if you do encounter them, they can be challenging to debug—so it's best to avoid these patterns, and we are improving the SDKs to eventually completely eliminate them. The first four are all variations on the theme of avoiding mutability; the last one is a performance issue.


### Don't modify a user object after passing it to the SDK


In all of the SDKs, there are several methods that accept a user properties object (such as when a client-side/mobile SDK is initialized, or when a server-side SDK evaluates a flag). Once you have passed a user object to the SDK, you should assume that the SDK may maintain a reference to it for an unknown amount of time and it is _not safe to modify it_ (if it is, in fact, possible to modify it in the language you're using). Several things could happen if you do:



 	
  * If the SDK has not yet finished a feature flag evaluation based on the original user, you could end up with flag values based on the modified user properties.

 	
  * If the SDK has generated analytics events referencing this user, but has not yet sent them to LaunchDarkly, the events could end up containing the modified user properties.


Here's an example in Go of unintentionally modifying a user:


You may ask why the SDK doesn't simply do a deep copy of the user object, so that subsequent changes can't affect it. The reason is that this could impose significant overhead, in terms of both performance and memory, on applications that call SDK methods frequently and use many user properties; since the SDK has no way of knowing whether an application might modify the user, it would have to copy the user on _every_ method call. Treating the user as immutable once created is greatly preferable, since then it is always safe to reuse the same object, and the application only needs to incur extra overhead when it is deliberately creating a new set of user properties. So we are moving in that direction in all of our SDKs.

Here are some more specific issues broken down by platform:



 	
  * **Go:** The [User](https://godoc.org/gopkg.in/launchdarkly/go-server-sdk.v4#User) struct is passed by value, not by reference, but it is still not safe to modify for two reasons. First, its optional string properties are really string _pointers_; modifying the value at the pointer, rather than the pointer itself, will affect all copies of the User. Second, custom attributes are in a map; maps are passed by reference, and do not allow simultaneous reads and writes. If you modify the Custom map while the SDK is attempting to copy the user data into analytics events, it will cause an error and the event data will not be sent at all.

 	
    * In a future major version of the Go SDK, we will be replacing the public User fields with a builder pattern that makes the attributes immutable once set.




 	
  * **Java:** The [LDUser](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDUser.html) object is immutable. However, see the next section regarding custom attributes.

 	
  * **.NET:** The [User](https://launchdarkly.github.io/dotnet-server-sdk/html/T_LaunchDarkly_Client_User.htm) object is currently mutable via [extension methods](https://launchdarkly.github.io/dotnet-server-sdk/html/T_LaunchDarkly_Client_UserExtensions.htm) like AndName.

 	
    * As of .NET SDK 5.7.1, you should use [User.Builder](https://launchdarkly.github.io/dotnet-server-sdk/html/M_LaunchDarkly_Client_User_Builder_1.htm) instead of the mutative extension methods.

 	
    * In a future major version of the .NET SDK, the User extension methods will be removed from the public API.




 	
  * **Ruby, Python, and all JavaScript-based SDKs:** The user object in these languages is just an associative array/dictionary, which is mutable.

 	
    * In future major versions of these SDKs, we will probably use a custom class instead of a generic object. This will be a less convenient syntax for developers who are used to simply declaring key-value pairs inline, but it is safer and will also make it harder to accidentally use an invalid property name.




 	
  * **C/C++:** All user properties are currently mutable.

 	
  * **PHP:** Mostly safe—the LDUser object is immutable. However, see the next section regarding custom attributes.

 	
  * **Xamarin:** Not an issue—[users](https://launchdarkly.github.io/xamarin-client-sdk/html/T_LaunchDarkly_Client_User.htm) are entirely immutable in the Xamarin SDK.




### Don't modify a value _within_ a complex user attribute after passing the user to the SDK


This is a subtler version of the previous issue. In the LaunchDarkly model, user custom attributes can be of any type supported by JSON. Two of those types, **array** (a.k.a. list) and **object** (a.k.a. hash/map/dictionary), correspond to data structures that in many languages are passed by reference and are mutable. So, for instance, in Node.js you could accidentally modify a user by modifying an array element, like this:


This is a problem for the same reasons described above. The issue is slightly different by platform:



 	
  * **Go:** If you set a user custom attribute to a slice (type []interface{}) or a map (type map[string]interface{}), it is mutable. Avoid modifying the slice or map after the SDK has seen the user.

 	
    * A future major version of the Go SDK will use a builder pattern for users, with an immutable representation of arrays and maps.




 	
  * **Java:** User custom attributes [can be set](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDUser.Builder.html#custom-java.lang.String-com.google.gson.JsonElement-) to an arbitrary JSON value of type JsonElement. If this value is really a JsonArray or JsonObject, it is mutable.

 	
    * As of Java SDK 4.9.0, you should use [the overload](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDUser.Builder.html#custom-java.lang.String-com.launchdarkly.client.value.LDValue-) that takes the immutable type [LDValue](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/value/LDValue.html) instead of JsonElement to avoid this issue.

 	
    * In a future major version of the Java SDK, JsonElement will be removed from the public API.




 	
  * **.NET:** Similar to Java: custom attributes [can be set](https://launchdarkly.github.io/dotnet-server-sdk/html/M_LaunchDarkly_Client_UserExtensions_AndPrivateCustomAttribute.htm) to the type JToken, which has mutable array and object subclasses.

 	
    * As of .NET SDK 5.7.1, you should use the [builder method](https://launchdarkly.github.io/dotnet-server-sdk/html/M_LaunchDarkly_Client_IUserBuilder_Custom.htm) for the immutable type [LdValue](https://launchdarkly.github.io/dotnet-server-sdk/html/T_LaunchDarkly_Client_LdValue.htm) instead of JToken to avoid this issue.

 	
    * In a future major version of the .NET SDK, JToken will be removed from the public API.




 	
  * **Ruby, Python, all JavaScript-based SDKs, and PHP:** Custom user attributes can use the language's built-in data structures for arrays/lists and objects/maps/dictionaries, which are mutable.

 	
    * Future major versions of these SDKs will use a builder pattern for users, with immutable representations of arrays and maps.




 	
  * **C/C++:** Custom user attributes use the LDJSON* type, which is mutable.

 	
  * **Xamarin:** Not an issue—the Xamarin SDK uses only the immutable [LdValue](https://launchdarkly.github.io/xamarin-client-sdk/html/T_LaunchDarkly_Client_LdValue.htm).




### Don't modify a value within a complex _flag value_ after receiving it


This is similar to the previous issue, since it involves the mutability of JSON array/object data structures. Like custom attributes, flag variations can have values of any JSON type, so the result of a flag evaluation could be an array (list) or object (hash/map/dictionary). This value lives inside the SDK, in the flag data that it received from LaunchDarkly; if you modify one of its array elements or object properties, you are modifying the SDK's internal data, so subsequent flag evaluations may be incorrect.


Most applications do not use complex data types for flag variations, but if you do, you should be careful not to modify values in this way. More specifically, by platform:



 	
  * **Go:** The return value of [JsonVariation](https://godoc.org/gopkg.in/launchdarkly/go-server-sdk.v4#LDClient.JsonVariation) or [JsonVariationDetail](https://godoc.org/gopkg.in/launchdarkly/go-server-sdk.v4#LDClient.JsonVariationDetail) is an interface{}, which could either be a primitive type, a slice (type interface{}), or a map (type map[string]interface{}).

 	
    * A future version of the Go SDK will add an immutable value type to use instead of interface{}. In the next backward-incompatible major version, the methods that use interface{} will be removed.




 	
  * **Java:** The return value of [jsonVariation](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDClientInterface.html#jsonVariation-java.lang.String-com.launchdarkly.client.LDUser-com.google.gson.JsonElement-) or [jsonVariationDetail](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDClientInterface.html#jsonVariationDetail-java.lang.String-com.launchdarkly.client.LDUser-com.google.gson.JsonElement-) is a JsonElement, which could be a mutable JsonArray or JsonObject.

 	
    * As of Java SDK 4.9.0, you should use jsonValueVariation or [jsonValueVariationDetail](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDClientInterface.html#jsonValueVariationDetail-java.lang.String-com.launchdarkly.client.LDUser-com.launchdarkly.client.value.LDValue-) instead; these return an immutable [LDValue](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/value/LDValue.html).




 	
  * **.NET:** Similar to Java: [JsonVariation](https://launchdarkly.github.io/dotnet-server-sdk/html/M_LaunchDarkly_Client_ILdClient_JsonVariation_1.htm) and [JsonVariationDetail](https://launchdarkly.github.io/dotnet-server-sdk/html/M_LaunchDarkly_Client_ILdClient_JsonVariationDetail_1.htm) can return a JToken, which could contain a mutable value.

 	
    * As of .NET SDK 5.7.1, you should use [the overloads of these methods](https://launchdarkly.github.io/dotnet-server-sdk/html/M_LaunchDarkly_Client_ILdClient_JsonVariation.htm) that use an immutable [LdValue](https://launchdarkly.github.io/dotnet-server-sdk/html/T_LaunchDarkly_Client_LdValue.htm) instead of JToken.




 	
  * **Ruby, Python, all JavaScript-based SDKs, and PHP:** These SDKs are loosely typed and have only a single variation method, which could return a mutable array or object.

 	
    * In a future major version, this will probably be addressed by having one method that returns an immutable type _containing_ any kind of value, and another method that returns a plain value (which would be deep-copied if it is an array or object).




 	
  * **C/C++:** The LDJsonVariation method returns an LDJSON*, which is mutable.

 	
  * **Xamarin:** Not an issue, as above.


As discussed in the first section on users, simply adding a deep-copy step for every flag evaluation would impose an unwanted performance and memory burden on applications that are not doing anything unsafe. Our preferred approach is to move toward using immutable types that can always be safely passed by reference.


### Don't modify a value within a complex _default value_ after passing it to the SDK


This is similar to the previous issue, but instead of it being a value that was provided by the SDK, it is the application default value that your code provides as a fallback for flag evaluations. Since this is normally of the same type as the expected flag variations, for a complex flag it could be an array or object value. The SDK includes this default value in analytics events, so if the application modified it later, the events could be inaccurate. Worse, if there is an error condition so that the SDK really has to _use_ the default value, it will return the same object to the application—which could then be unintentionally modifying the result it just got. For instance, in Node.js:


Most applications do not use complex data types for flag variations, but if you do, you should be careful not to modify an already-used default value in this way. The per-platform details are the same as in the previous section (e.g., in Java, use [jsonValueVariation](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDClientInterface.html#jsonValueVariation-java.lang.String-com.launchdarkly.client.LDUser-com.launchdarkly.client.value.LDValue-) instead of [jsonVariation](https://launchdarkly.github.io/java-server-sdk/com/launchdarkly/client/LDClientInterface.html#jsonVariation-java.lang.String-com.launchdarkly.client.LDUser-com.google.gson.JsonElement-)).


### Avoid performance bottlenecks from unnecessary repetitive flag evaluations


The short version of this issue is that instead of doing this (in, for instance, Java)—


—it's preferable to do this:


This may seem obvious, since every flag evaluation has some processing overhead and you don't want to multiply the overhead unnecessarily. What may not be obvious is that—on a multithreaded platform—even if you found the overhead to be acceptable in the first code sample above, you might experience a much more severe slowdown as usage of the application increases, because of a concurrency bottleneck.

There are two resources within the SDK that are shared across threads(*): the flag data and the analytics event data. The flag data is almost always read-only, so it is optimized for reads and is not a major source of contention between threads. However, if analytics events are enabled, every flag evaluation produces a unit of analytics data to be aggregated into the analytics events the SDK will eventually send to LaunchDarkly. The analytics event buffer is therefore a shared read-write resource, with a high potential for contention between threads.

_(* Or, in Go, goroutines; we'll use the word "thread" here for simplicity.)_

To avoid having threads slow each other down too much as they try to access the analytics data, the SDKs generally use a multi-stage approach where the application threads interact only with a fast data structure—a queue—which is then consumed by a worker thread that does the slower work of aggregating the data. In current versions of the SDKs, this queue is non-blocking, so if evaluations are being done faster than the events can be processed, it will discard the newest analytics data rather than blocking any application thread.

However, since the SDK does need to get the data into one place somehow, it is not possible to _completely_ avoid contention for the shared queue. If an application is evaluating flags at an extremely high rate, many times per thread—as in the first code sample—on a large number of threads, it is possible to produce a noticeable slowdown that is out of proportion to the overhead of evaluations within a single thread, as the threads compete for the chance to even _look at_ the queue.

The code sample here is a little silly, but don't let that distract you; if the call to `boolVariation` happened deeper inside a chain of method calls, you might not notice that these redundant evaluations are happening. If your application is going to process heavy traffic on many threads, you should assume that every evaluation may need to contend at least briefly for a lock. If you think a code path will be executed many times with the same flag value, it might make more sense for you to evaluate the flag once and pass the value down as a parameter or thread-local variable.

This is mostly an issue because of analytics events, which you can disable if you need to. That said, most LaunchDarkly users find analytics data to be a powerful tool. Furthermore, even if this concurrency issue didn't exist, it's a best practice to avoid redundant evaluations if only because they make data evaluation more complicated. Did a user interact with this page once, or 100,000 times? If you're dealing with redundant evaluations, it's hard to tell!


### Conclusion


LaunchDarkly helps teams around the world control and manage their software. To make your experience using LaunchDarkly as easy and effective as possible, be sure to avoid these concurrency pitfalls.
