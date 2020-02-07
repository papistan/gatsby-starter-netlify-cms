---
author: dparzych
comments: false
date: 2019-12-17 15:00:36+00:00
layout: post
link: https://launchdarkly.com/blog/deploying-launchdarkly-with-pivotal-cloud-foundry/
slug: deploying-launchdarkly-with-pivotal-cloud-foundry
title: Deploying LaunchDarkly with Pivotal Cloud Foundry
wordpress_id: 194039
categories:
- Feature Management
---

A successful CI/CD pipeline uses many different tools and services including cloud platforms, containers, monitoring, logging, and feature management. Making sure the tools you choose work together is an important aspect. Pivotal Cloud Foundry is one tool that LaunchDarkly customers include in their toolbox.

Pivotal Cloud Foundry (PCF) is a multi-cloud platform based on Cloud Foundry, an open-source Platform as a Service (PaaS). Individuals and companies of all sizes use PCF to continuously delivery apps in a highly scalable, secure way.

This guide walks you through how to configure LaunchDarkly to work with your Pivotal Cloud Foundry applications.


### Prerequisites





 	
  * LaunchDarkly account

 	
  * Pivotal account

 	
  * An application running in Pivotal (our examples assume you are using Maven or Gradle, but any build strategy will work)




### Initial setup


Setting up LaunchDarkly to control your first feature flag takes only a few minutes.


#### Setting up LaunchDarkly


Create a new project by navigating to "Account Settings" in the bottom left navigation pane.

[![Screenshot of account settings location within GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Account-settings.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Account-settings.png)

Click the “New Project” button.

[![Image of new project button in the GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/New-Project-button.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/New-Project-button.png)

Enter a name and any tags to be associated with the project. The key will be auto-generated, you can modify if desired.

[![screenshot of create a project screen in GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Create-a-project.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Create-a-project.png)

Once the project has been saved, copy your SDK key – you will need that below.

[![Screenshot of environments and SDK keys from GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/SDK-Key.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/SDK-Key.png)


#### Within your application


First, add the SDK to your project:



Now import the LaunchDarkly client in your application code:

    
    import com.launchdarkly.client.*;


Next, configure the LaunchDarkly Client with your SDK  key (from the steps above) and create the client:

    
    LDClient ldClient = new LDClient(YOUR_SDK_KEY);




### Creating your first feature flag




#### Within LaunchDarkly


To [create a feature flag](https://docs.launchdarkly.com/docs/creating-a-feature-flag), navigate to your feature flag [dashboard](https://app.launchdarkly.com/).

Click "New" or “Create Feature Flag”. This will prompt you to create a feature flag.

[![Create new feature flag page from GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Empty-Feature-Flags.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Empty-Feature-Flags.png)

In the "Create a feature flag" area, you can specify attributes for your new feature flag, including name, description, and type. These attributes help you manage the feature flag and customize it to your use case.

[![Fields from the create a feature flag page in GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/create-a-feature-flag.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/create-a-feature-flag.png)

**Name**: Give your feature flag a meaningful human-friendly name. This name will appear on the feature flag dashboard.

**Key**: The key will be used to reference the flag in your code. It may be customized in any way. Keys must be unique.

**Description**: Describe the purpose of the flag to help others understand what the flag does.

**Tags**: Labels are used to categorize a flag and control permissions using custom roles. You can tag flags with a team such as marketing or operations to determine who has read or write access to control the flag.

Read more on [custom roles and tags](https://docs.launchdarkly.com/docs/custom-roles).

**Flag Variations: **Flags can be either Boolean or multivariate. A Boolean flag can return either true or false.  With a multivariate flag, you can define two or more custom variations for a feature. These variations can be strings, numbers, JSON objects, or JSON arrays.

Read more on [flag variations](https://docs.launchdarkly.com/docs/managing-variations).

Note: JSON names require double quotes, even though JavaScript the language does not. LaunchDarkly will validate your input as JSON if formatted correctly within double quotes.

**This is a permanent flag:** Feature flags can be temporary or permanent. Mark the flag as permanent if you intend it to keep it in your code long-term (e.g., a flag to enable maintenance mode). LaunchDarkly will not prompt you to remove permanent flags, even if one variation has been rolled out to all of your users.

**Make this flag available to client-side SDKs:** Once the flag is saved, you will see the targeting screen. There are multiple ways you can target users. You can target individuals or groups of users, users based on attributes, or a random percentage of users.  For our example, we selected a percent-based rollout where the flag would be evaluated as true for 50% of the users and false for 50% of the users.

[![Fields available on the targeting page in the GUI](https://blog.launchdarkly.com/wp-content/uploads/2019/06/YourPercentageRolloutFlag.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/YourPercentageRolloutFlag.png)

Learn more about [targeting and identifying users.](https://docs.launchdarkly.com/docs/targeting-users)


#### In your app


The feature key created above will be used in your application code to check which variation of a feature flag a user will receive by calling the variation method (or boolVariation in typed languages).

The variation is combined with the user object. LaunchDarkly uses the user key to identify each user. The key needs to be unique to each user—a database key, an email address (though PII is discouraged), or a hash of an email address works. In this example, we create a random user ID for the userKey.

    
    /**
     * A web controller that displays a flag evaluation.
     */
    @Controller
    public static class DemoController {
    @ResponseBody
    @GetMapping(value = "/", produces = MediaType.TEXT_HTML_VALUE)
    public String root() {
    String userKey = UUID.randomUUID().toString();
    String flagKey = "your-flag-key";
    LDUser ldUser = new LDUser.Builder(userKey).build();
    


This sample web page will randomly display a line of text stating the name of the flag, whether it returned true or false and the unique user key that was generated.




#### Validate your flag


Once you're ready to test your integration, head over to the [debugger](https://docs.launchdarkly.com/docs/debugger) in LaunchDarkly to get a real-time view of your feature flag requests as they're received. The debugger will show the total number of evaluations while on an active tab. If the debugger was opened after loading your application you will not see flag evaluations listed.

Open a browser and navigate to your application. Toggle the feature on and off while loading/reloading the page.

Loading our sample application you will see one of the following two statements:

"Flag **your-percentage-rollout-flag-key **serves **false **to user **a4d77f6-f441-4514-9a3c-cca72031b1c5**"

Or

"Flag **your-percentage-rollout-flag-key **serves **true **to user **7377aef3-b810-467e-9b33-b970b71e7573"**



[![Debugger results showing the flag was evaluated](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Debugger.png)](https://blog.launchdarkly.com/wp-content/uploads/2019/06/Debugger.png)

That's it! Now you can manage the feature on your dashboard. Read on to see how to do [controlled rollouts](https://docs.launchdarkly.com/docs/targeting-users) and [A/B tests](https://docs.launchdarkly.com/docs/running-ab-tests) without redeploying your application!
