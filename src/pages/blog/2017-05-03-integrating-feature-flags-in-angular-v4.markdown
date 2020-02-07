---
author: arnold
comments: false
date: 2017-05-03 17:10:37+00:00
layout: post
link: https://launchdarkly.com/blog/integrating-feature-flags-in-angular-v4/
slug: integrating-feature-flags-in-angular-v4
title: Integrating Feature Flags in Angular v4
wordpress_id: 1552
categories:
- Continuous Delivery
- Feature Management
tags:
- Angular
- continuous delivery
- feature flags
- LaunchDarkly
---

A little while ago, we blogged about [eliminating risk in your AngularJS applications](https://blog.launchdarkly.com/implementing-feature-flags-in-an-angular-e-commerce-app/) by leveraging feature flags. Like all good web frameworks Angular continues to release new versions providing opportunities to tweak and update your code. The benefits of Angular over its predecessor include a built-in compiler,type enforcement, and a complete re-write in Typescript. All valuable of updates for reducing agony within the software development lifecycle.

If you’re thinking of making the switch to Angular, or are already using it, LaunchDarkly is here to help you eliminate the risk all the way from your initial migration to future successful launches. In this article, we’ll discuss how to eliminate risk and deliver value in your Angular project.

We’ll build on [Tour of Heroes](https://github.com/johnpapa/angular-tour-of-heroes) (which we’ll refer to as TOH from here on out), a demonstrative Angular app which showcases the framework’s basic concepts. Essentially, TOH is a live roster of superheroes, including search functionality and the ability to modify hero details. To learn more about TOH, and to get familiar with Angular, check out the [official tutorial](https://angular.io/docs/ts/latest/tutorial/).

**Creating our Feature Flags**
Suppose we want to limit the usage of our search and modify features to a certain subset of our users. To achieve this, we’ll create two feature flags, toh-search  and toh-modify . In our case, we’ll allow logged in users access to search, and only the administrator will be able modify heroes.

[caption id="attachment_1553" align="aligncenter" width="966"][![](https://blog.launchdarkly.com/wp-content/uploads/2017/04/toh-search.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/04/toh-search.png) An implementation of toh-search in the LaunchDarkly console[/caption]

**Integrating**

Now, we’ll create a service which handles everything [LaunchDarkly’s JavaScript SDK](https://www.npmjs.com/package/ldclient-js) will throw at us. Note: for simplicity, we use a dummy user-switching feature (located in the user component of the project folder).

    
    /app/launchdarkly.service.ts



    
    import { Injectable } from '@angular/core';
    import { Subject } from 'rxjs/Subject';
    import { initialize, LDClient, LDFlagSet } from 'ldclient-js';
    
    @Injectable()
    export class LaunchDarklyService {
      ldClient:LDClient;
      flags:LDFlagSet;
      flagChange:Subject<Object> = new Subject<Object>();
      constructor() {
        this.flags = {'toh-modify': false, 'toh-search': false};
    
        this.ldClient = initialize("YOUR-CLIENT-SIDE-ID",
          { key: "SAMPLE-USER-KEY", anonymous: true });
    
        this.ldClient.on('change', (flags) => {
          if(flags['toh-modify'] !== undefined) {
            this.flags['toh-modify'] = flags['toh-modify'];
          }
          if(flags['toh-search'] !== undefined) {
            this.flags['toh-search'] = flags['toh-search'];
          }
          this.flagChange.next(this.flags);
          console.log("Flags updated.")
       });
    
       this.ldClient.on('ready', () => {
         this.setFlags();
       })
      }
    
      setFlags() {
        this.flags = this.ldClient.allFlags();
        console.log("Flags initialized.");
      }
    
      changeUser(user) {
        if(user !== "Anonymous") {
          this.ldClient.identify({key: user, name: user, anonymous: false});
        }
        else {
          this.ldClient.identify({key: 'anon', anonymous: true});
        }
      }
     }


LaunchDarklyService’s constructor starts by initializing the SDK, and follows up by calling the built-in on method, which will update the feature flag values within our app whenever the user is changed, or the feature flag configurations are modified. This is handled by a Subject-typed variable,  flagChange , which will later be subscribed to by in the app’s components.
With our service functional, we’re now able inject it as a provider into TOH’s “search” and “hero” components, granting them full access to our feature flags!

    
    /app/hero-search.component.ts
    
    @Component({
      ...
      providers: [HeroSearchService, LaunchDarklyService]
    })
    export class HeroSearchComponent implements OnInit {
      show: boolean;
      _subscription: any;
      heroes: Observable<Hero[]>;
      private searchTerms = new Subject<string>();
    
      constructor(
        private ld: LaunchDarklyService,
        private heroSearchService: HeroSearchService,
        private router: Router) {
          this.show = ld.flags['toh-search'];
          this._subscription = ld.flagChange.subscribe((flags) => {
            this.show = flags['toh-search'].current;
          })
      ...
        }
    



    
    /app/hero-search.component.html
    
    <div *ngIf="show" id="search-component">
      <h4>Hero Search</h4>
      <input #searchBox id="search-box" (keyup)="search(searchBox.value)" />
      <div>
        <div *ngFor="let hero of heroes | async"
             (click)="gotoDetail(hero)" class="search-result" >
          {{hero.name}}
        </div>
      </div>
    </div>
    


In the hero-search component, we subscribe to the aforementioned flagChange , which will let Angular know that the search component should be toggled whenever the respective feature flag configuration is changed. The hero component is modified in a similar fashion to introduce the toh-modify  flag.

**See it in action!**

Search:

[video width="1900" height="800" mp4="https://blog.launchdarkly.com/wp-content/uploads/2017/04/toh-search.mp4"][/video]

Modify:

[video width="1900" height="800" mp4="https://blog.launchdarkly.com/wp-content/uploads/2017/04/toh-modify.mp4"][/video]

Be sure to check out the complete project on [GitHub](https://github.com/launchdarkly/ld-tour-of-heroes), we’d love to see what other features you can build into Tour of Heroes!
