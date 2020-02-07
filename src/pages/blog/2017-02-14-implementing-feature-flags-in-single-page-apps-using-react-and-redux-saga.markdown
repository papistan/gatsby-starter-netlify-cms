---
author: justinucd
comments: false
date: 2017-02-14 16:59:05+00:00
layout: post
link: https://launchdarkly.com/blog/implementing-feature-flags-in-single-page-apps-using-react-and-redux-saga/
slug: implementing-feature-flags-in-single-page-apps-using-react-and-redux-saga
title: Implementing feature flags in single page apps, using React and Redux Saga
wordpress_id: 1395
categories:
- Feature Management
tags:
- Angular
- Ember
- feature flag
- front-end
- javascript
- React
- react redux
- React Router
- Redux
- single page apps
---

Built on frameworks like [React](https://facebook.github.io/react/), [Angular](https://angularjs.org/), and [Ember](http://emberjs.com/), single page apps (SPA) are becoming the new norm for modern applications. They center around dynamically updating a single HTML page via AJAX and HTML5 to deliver a more fluid and faster user experience. This introduces some new complexity when it comes to controlling access to front-end features, specifically via feature flags.

Feature flags (toggles) are used to gate access to particular code snippets, allowing you to control a feature’s rollout, target specific users, and kill a feature in production. The challenge with feature flagging single page apps is handling the state transformations (the changes in a webpage’s DOM) in a way that maintains performance and a fluid user experience.

This article discusses how to feature flag in a React single page app to show best practices. More specifically, we demonstrate feature flagging using [LaunchDarkly’s JavaScript SDK](https://github.com/launchdarkly/js-client).

**Feature Flagging in Single Page Apps**

With the help of React Router, creating a single page application can be a very quick and easy process, allowing developers to minimize risk and test features without degrading the user experience. We use Redux Sagas to handle asynchronous actions, which is perfect for integrating our app with the LaunchDarkly JavaScript SDK.

**Feature Flags**

In our app, we use two feature flags, user-type and header-bar-color. The user-type feature flag controls the content that is displaying depending on the group of current logged in user, while header-bar-color returns a hex code to toggle the color of the navigation bar.

An implementation of header-bar-color might look something like this:

[![](https://blog.launchdarkly.com/wp-content/uploads/2017/02/header-bar-color.png)](https://blog.launchdarkly.com/wp-content/uploads/2017/02/header-bar-color.png)

**Integrating Feature Flags with Redux Sagas**

We handle the asynchronous process of requesting a LaunchDarkly feature flag by using Redux Sagas. The workflow begins in the App component of our SPA, where we dispatch an action to initialize the LaunchDarkly client.

    
    /app/components/App.js
    class App extends Component {
      componentDidMount () {
        this.props.dispatch(ldInitRequest())
      }
      render () {
      …
      }
    }
    
    /app/actions/index.js
    export function ldInitRequest() {
      return {type: LD_INIT_REQUEST}
    }


Then, we can use a saga as middleware to wait for an initialization request to be received, using redux-saga’s takeEvery module, which will call an effect, initLD.

    
    /app/sagas/index.js
    export function * watchInitLD () {
      yield takeEvery(LD_INIT_REQUEST, initLD)
    }
    


The effect will call getLD, a function which creates a promise, waiting for the LaunchDarkly client to be ready for flag requests. Since the user is anonymous, we can generate a random token to be used as their key.

    
    /app/sagas/index.js
    export function * initLD () {
      let user = {key:Math.random().toString(36).substring(7), anonymous:true}
      ld = ldClient.initialize(YOUR_ENVIRONMENT_KEY, user)
      const flag = yield call(getLD, user)
      yield put({type: LD_INIT, ld: ld, flag: flag})
    }
    
    function getLD () {
      var ldPromise = Promise.promisify(ld.on)
      return ldPromise('ready').then(function () {
        return ld.allFlags()
      })
    }


Once the client is ready, the effect will send the action off to our reducer, to store the client and current feature flag state in props.

    
    /app/reducers/index.js
    function reducer (state = initialState, action) {
      switch (action.type) {
        case LD_INIT:
          return {...state, ld: action.ld, flag: action.flag, headerColor: action.headerColor}
        …
        default:
          return state
      }


Now that the LD client is initialized, and stored in our props, we can define a process to update our flag whenever the current user changes (logging in or out, for example). We take advantage of the fact that we’re already using sagas to asynchronously handle user authentication. When logging in, the authorize effect is called to ensure the login data is correct. When authorization is complete, we’ll make a call to idLD. This will identify a new user in our LaunchDarkly client, and send the correct flag to the reducer for our newly logged in user. Logging out works in a similar fashion. (Note: We make use of some utility functions defined in auth, which return user information from our local storage.)

    
    /app/sagas/index.js
    export function * authorize ({username, password, isRegistering}) {
      try {
        ...
      } catch (error) {
        ...
      } finally {
        // When done, we tell Redux we're not in the middle of a request any more and
        // update the feature flag
        let user = {key: auth.getToken(), custom: {groups:auth.getGroup()}, anonymous:false}
        let flags = yield call(idLD, user)
        console.log(flags['header-bar-color'])
        yield put({type: SENDING_REQUEST, sending: false, flag: flags['user-type'], headerColor: flags['header-bar-color']})
      }
    }
    
    function idLD (user) {
      var ldPromise = Promise.promisify(ld.identify)
      return ldPromise(user, null).then(function () {
        return ld.allFlags()
      })
    }


So, what do we do with the flags stored in our props? Well, in our Home component, we’ll render a different page depending on the flag that was received. In our case, if a fallback flag is received, the “Anonymous” page will be shown no matter who is logged in.

    
    /app/components/Home.js
    class Home extends Component {
      render () {
        switch(this.props.data.flag) {
          case 2: 
            return(<Admin />)
          case 1: 
            return(<User />)
          case 0:
          default: 
            return(<Anonymous />)
        }
      }
    }


Meanwhile, every time a page is loaded, the Nav component takes in the headerColor prop and changes the background of our navbar to said color.

    
    /app/components/common/Nav.js
    class Nav extends Component {
      ...
      render () {
        …
        let color = this.props.headerColor
        return (
          <div style={{backgroundColor:color}} className='nav'>
            ...
          </div>
        )
      }
    


**See it in action**

[video width="3183" height="1576" webm="https://blog.launchdarkly.com/wp-content/uploads/2017/02/header-bar-color-demo.webm"][/video]

**What’s next?**
There are many ways to feature flag within a single page app, depending on your case and the complexity of your features. You can also check out [this](https://github.com/TrueCar/react-launch-darkly) repo by TrueCar, which provides another avenue for feature flagging in React Redux.

Want to try out this feature flagging in React for yourself? Check out the [open source repo](https://github.com/launchdarkly/saga-feature-flow)!

----

_**Primary Contributor:  **[Arnold Trakhtenberg](https://github.com/atrakh/), Engineering Content Consultant at LaunchDarkly_
