react-project-setup v1
======================

This repository aims to collect resources, opinions and conclusions surrounding react related topics, to provide a guideline for setting up react projects and to provide an example implementation.

<!-- TOC -->

- [1. TL;DR](#1-tldr)
- [2. Introduction](#2-introduction)
- [3. Language](#3-language)
    - [3.1. ES6 (ECMAScript 2015)](#31-es6-ecmascript-2015)
        - [3.1.1. Resources](#311-resources)
    - [3.2. Babel](#32-babel)
        - [3.2.1. Resources](#321-resources)
    - [3.3. Static Typing](#33-static-typing)
        - [3.3.1. Resources](#331-resources)
    - [3.4. Typescript](#34-typescript)
        - [3.4.1. Resources](#341-resources)
- [4. Package manager - npm vs. yarn](#4-package-manager---npm-vs-yarn)
- [5. Build process](#5-build-process)
    - [5.1. Webpack](#51-webpack)
    - [5.2. gulp](#52-gulp)
    - [5.3. Conclusion](#53-conclusion)
- [6. create-react-app](#6-create-react-app)
    - [6.1. Resources](#61-resources)
- [7. Styling](#7-styling)
    - [7.1. CSS Modules](#71-css-modules)
    - [7.2. SCSS](#72-scss)
    - [7.3. Conclusion](#73-conclusion)
- [8. State Management](#8-state-management)
    - [8.1. Resources](#81-resources)
    - [8.2. Redux](#82-redux)
        - [8.2.1. redux-thunk](#821-redux-thunk)
        - [8.2.2. Other useful tools and approaches](#822-other-useful-tools-and-approaches)
        - [8.2.3. Resources](#823-resources)
    - [8.3. Immutable State](#83-immutable-state)
        - [Resources](#resources)
    - [8.4. Alternatives](#84-alternatives)
        - [8.4.1. Resources](#841-resources)
    - [8.5. Conclusion](#85-conclusion)
- [9. Code Conventions](#9-code-conventions)
    - [9.1. Lint](#91-lint)
    - [9.2. Prettier](#92-prettier)
- [10. Testing](#10-testing)

<!-- /TOC -->

# 1. TL;DR

# 2. Introduction

Before all the specific topics, focus on [learning React](https://github.com/petehunt/react-howto). After all, that's what we want to use to build our frontend applications. By the way, there is an [awesome React & Redux blog](http://blog.isquaredsoftware.com/), made by [Mark Erikson](https://github.com/markerikson), definitely a recommendation.

# 3. Language

## 3.1. ES6 (ECMAScript 2015)

Really? Do you doubt using ES6 makes sense? [Here](http://blog.thefirehoseproject.com/posts/12-reasons-es6-future-javascript-web-development/) is a tiny introduction to new features of ES6 and [here](http://es6-features.org/) you find a whole list of cool, sparkly things you can do with JavaScript. We can even go further and check out features from ES7 and ES8 - more about that in the Babel section. The current state of ECMAScripts' development can be found [here](https://github.com/tc39).

### 3.1.1. Resources

* http://blog.thefirehoseproject.com/posts/12-reasons-es6-future-javascript-web-development/
* https://tech.io/playgrounds/6439/modern-es6-javascript-pt--1
* http://es6-features.org/
* https://github.com/tc39

## 3.2. Babel

So we want to use the features of ES 6, 7 and 8, right? Do you remember the days when the same code produced different results in Firefox, Chrome and the Inter Explorer? That still happens as we know, but thanks to [Babel](https://babeljs.io/) and other frameworks and polyfills, this is not a major headache anymore, at least not compared to the situation a few years ago. Of course not all the cool shiny features are implemented in the browsers yet. This is were [Babel](https://babeljs.io/#es2015-and-beyond) shines, it [transpiles](https://scotch.io/tutorials/javascript-transpilers-what-they-are-why-we-need-them) ES 6+ Code down to ES 5 Code, so it can be used in all the browsers.

Because Babel has been around since forever, from a JavaScript frontend developers perspective, you can find a ton of resources of how to use it and there are so many [projects](https://babeljs.io/users/) using it, it really is [everywhere](https://babeljs.io/docs/setup/). You usually don't have to learn how to use the [Babel CLI](https://babeljs.io/docs/setup/#installation) but rather setup Babel being used in a Webpack workflow - more on that in the Webpack section.

### 3.2.1. Resources

* https://babeljs.io/
* https://scotch.io/tutorials/javascript-transpilers-what-they-are-why-we-need-them

## 3.3. Static Typing

Do we need type checking in JS? The short answer: [yes](https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007#1a07), the long one: [yes, but only for bigger projects](https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007#f51a). Also take a look [here](https://stackify.com/typescript-vs-javascript-migrate/) - scroll down to "When To Choose: TypeScript vs. JavaScript". 

Right now there two competitors - actually there are many more if you consider languages that have totally different syntax and eco system as JavaScript (e.g. [Elm](http://elm-lang.org/)). If you want to stay with JavaScript [TypeScript](https://www.typescriptlang.org/) and [Flow](https://flow.org/) are the most popular options. While both tools have their [advantages](https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007#b560), it seems that TypeScript is gaining more and more ground in the [comparison](https://github.com/niieani/typescript-vs-flowtype). Also check out this [discussion on TypeScript vs. Flow](https://www.reddit.com/r/javascript/comments/7bfwpl/flow_vs_typescript/).

With version 2 of Googles Framework [AngularJS](https://angularjs.org/), the team decided to fully work [on top of TypeScript](https://vsavkin.com/writing-angular-2-in-typescript-1fa77c78d8e8). That's another game changer favouring TypeScript over Flow.

For bigger applications, complicated logic, big teams, or regularly changing team members, static typing your JavaScript code makes total sense and almost seems mandatory today. For a small private project, with just one contributor it seems unnecessary. Right now, for me, the go to choice is TypeScript. It seems to be faster, better maintained, you get typings for (almost) all the frameworks out there and have an excellent IDE integration.

### 3.3.1. Resources

* https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007
* https://blog.mariusschulz.com/2017/01/13/typescript-vs-flow
* https://www.reddit.com/r/javascript/comments/7bfwpl/flow_vs_typescript/
* https://github.com/niieani/typescript-vs-flowtype
* https://vsavkin.com/writing-angular-2-in-typescript-1fa77c78d8e8
* https://stackify.com/typescript-vs-javascript-migrate/

## 3.4. Typescript

So now that we decided to use TypeScript, how do we actually use it? It can be quite painful to refactor a complete code base, but there is a [guide](https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide) written by the TypeScript team. You would prefer starting with a clean slate, where the [examples](https://www.typescriptlang.org/samples/index.html) of TypeScript setups would help you. [Here](https://github.com/Microsoft/TypeScript-Babel-Starter/blob/master/README.md) is [one](https://github.com/Microsoft/TypeScript-Babel-Starter/blob/master/README.md) that helps you getting started with TypeScript and the still in pre-release existing [Babel 7](https://medium.com/@jdolle/babel-7-beta-instructions-aed5cf17048b) compiler. Babel 7 will be quite huge for TypeScript projects, because so far you needed to use the TypeScript compiler as an extra step, before using Babel. Now, Babel 7 can compile TypeScript directly. If you add React to the equation, there is even an easier way to setup your project, using [create-react-app](https://github.com/facebook/create-react-app) with a special [TypeScript script](https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter) - more about [create-react-app](https://github.com/facebook/create-react-app) in it's section.

### 3.4.1. Resources

* https://www.typescriptlang.org/samples/index.html
* https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide
* https://medium.com/@jdolle/babel-7-beta-instructions-aed5cf17048b
* http://artsy.github.io/blog/2017/11/27/Babel-7-and-TypeScript/
* https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter

# 4. Package manager - npm vs. yarn

# 5. Build process

## 5.1. Webpack

## 5.2. gulp

## 5.3. Conclusion

# 6. create-react-app

[create-react-app](https://github.com/facebook/create-react-app) is really practical it creates react apps with no build configuration. Meaning all the webpack tweaks, seting up a dev server etc. are taken care of - isn't that [awesome](https://medium.com/@tuchk4/why-i-love-create-react-app-e63b1be689a3)? The idea is that the scripts of create-react-app take care of all the configuration files and the basic folder structure. As long as you don't need something very specific or crazy, you should be fine staying with create-react-app.

There are additional scripts that boost the functionality of the create-react-scripts, for example one for [TypeScript support](https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter). You can even create your [own custom create-react-app template](https://auth0.com/blog/how-to-configure-create-react-app/).

Once you reach the point where the ready made template isn't doing it for you anymore, you [eject](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#npm-run-eject) create-react-app and all the managed configuration files will be available and you will be no longer using create-react-app. **This operation can not be undone!**

Even though there was a [plugin system](https://github.com/facebook/create-react-app/issues/670) discussed, it doesn't seem like they are going to work on that right now. But it seems like there might be an alternative: [Neutrino](https://neutrino.js.org/) - I will check that out soon.

Try to stay as long as possible with create-react-app. It keeps the project clean and abstracts build process configuration and are usually more or less the same anyway. Another benefit, create-react-app will take care of updating their scripts, which means you only have to update create-react-app to receive webpack, babel etc. updates.

## 6.1. Resources

* https://github.com/facebook/create-react-app
* https://medium.com/@tuchk4/why-i-love-create-react-app-e63b1be689a3
* https://hackernoon.com/simple-react-development-in-2017-113bd563691f
* https://www.fullstackreact.com/p/using-webpack-with-create-react-app/
* https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md
* https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter
* https://auth0.com/blog/how-to-configure-create-react-app/
* https://neutrino.js.org/

# 7. Styling

## 7.1. CSS Modules

## 7.2. SCSS

## 7.3. Conclusion

# 8. State Management

With React offering you render straight from props, you want to skip an internal component state whenever possible. Because the React component state can act quite [surprisingly](https://medium.com/javascript-scene/setstate-gate-abc10a9b2d82), especially for [beginners](https://blog.cloudboost.io/3-reasons-why-i-stopped-using-react-setstate-ab73fc67a42e). You should definitely read on [how to use setState correctly](https://medium.com/@baphemot/understanding-reactjs-setstate-a4640451865b).

No matter if you master React state or not, eventually, with a growing application, your component states will grow extraordinarily and you will have a hard time maintaining all the shared state passed down the component tree. Enter global state management. Even though there are [voices](https://medium.com/react-ecosystem/how-to-handle-state-in-react-6f2d3cd73a0c) and [projects](http://formidable.com/blog/2017/infinite-state-composition-with-freactal/) that question the current state of the art state management in React applications, you will most likely end up using a global state management, at least because your components share the same data.

Facebook itself is using the [Flux](https://github.com/facebook/flux/tree/master/examples/flux-concepts) Architecture. There are quite a few [implementations](https://medium.com/social-tables-tech/we-compared-13-top-flux-implementations-you-won-t-believe-who-came-out-on-top-1063db32fe73) of this principle. But as you can see by the date of those articles, the question "Which Flux Implementation Should I Use With React?" is not a very popular one anymore. The answer has been given (for now): [Redux](https://redux.js.org/).

## 8.1. Resources

* https://medium.com/javascript-scene/setstate-gate-abc10a9b2d82
* https://blog.cloudboost.io/3-reasons-why-i-stopped-using-react-setstate-ab73fc67a42e
* https://medium.com/@baphemot/understanding-reactjs-setstate-a4640451865b
* https://medium.com/react-ecosystem/how-to-handle-state-in-react-6f2d3cd73a0c
* http://formidable.com/blog/2017/infinite-state-composition-with-freactal/
* https://github.com/facebook/flux/tree/master/examples/flux-concepts
* https://medium.com/social-tables-tech/we-compared-13-top-flux-implementations-you-won-t-believe-who-came-out-on-top-1063db32fe73
* http://jamesknelson.com/which-flux-implementation-should-i-use-with-react/
* https://github.com/voronianski/flux-comparison

## 8.2. Redux

There are an [unlimited](https://github.com/happypoulp/redux-tutorial) [number](https://www.youtube.com/watch?v=1w-oQ-i1XB8) of [Redux](https://redux.js.org/docs/basics/) [tutorials](https://auth0.com/blog/redux-practical-tutorial/) and [examples](https://redux.js.org/docs/basics/ExampleTodoList.html) out there. [This one](https://www.valentinog.com/blog/react-redux-tutorial-beginners/) seems to be quite nice. If you check out tutorials, make sure they are rather up to date, otherwise they might use tools and APIs, that are not recommended anymore. It is worth mentioning that Redux is not limited to work with React, it can be used as the state management central for basically every other JavaScript based environment.

After you got a feeling for how it is to build an application with Redux and you are actually starting to use it in a bigger application, you will most likely encounter the case that you want to start some asynchronous action, like fetching data from the server, using an AJAX call. This topic is just one of many topics tackled by [store enhancers](https://github.com/reactjs/redux/blob/master/docs/Glossary.md#store-enhancer) and other projects surrounding, or building on top of Redux. Actually, [Mark mentioned](http://blog.isquaredsoftware.com/2018/02/marks-dev-links-002/#redux-addons-catalog-client-side-ui) his list of about [2000 Redux-related libraries and tools](https://github.com/markerikson/redux-ecosystem-links) that he "ran across and looked useful" - WTF!?

### 8.2.1. redux-thunk

You don't have to check out all of them - obviously. But there are quite a few projects that significantly improve or extend the work with Redux. Let's start with the modern classic the [redux-thunk](https://github.com/gaearon/redux-thunk#why-do-i-need-this) middleware.

It is one of the most popular and common choices among Redux middlewares. It "[...] allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods dispatch and getState as parameters."

Another similar approach, but using [generator functions](https://thejsguy.com/2016/10/15/a-practical-introduction-to-es6-generator-functions.html), is [redux-saga](https://redux-saga.js.org/docs/introduction/BeginnerTutorial.html). [Here](https://medium.com/react-native-training/redux-4-ways-95a130da0cdc) are some of those middlewares [compared](https://decembersoft.com/posts/what-is-the-right-way-to-do-asynchronous-operations-in-redux/). But with every topic, even those widely accepted tools have been [criticized](http://blog.isquaredsoftware.com/2017/01/idiomatic-redux-thoughts-on-thunks-sagas-abstraction-and-reusability/). It is supposed to be [too powerful](https://mobile.twitter.com/intelligibabble/status/800103510624727040), [wrongly used](https://stackoverflow.com/questions/35667249/accessing-redux-state-in-an-action-creator/35674575#35674575) and you might [not need them](https://medium.com/@thisismissem/you-may-not-need-to-thunk-f5dc7a6fcbca) at all.

So what to do? One of the criticizers [Leland Richardson](https://github.com/lelandrichardson) committed his own alternative [redux-pack](https://github.com/lelandrichardson/redux-pack). What I like about it: 

* It does give you an alternative to dispatching multiple actions, for what is actually one action.
* It does solve the issue of the store being in an unstable state, because of sequentially dispatched actions.

What I don't like:

* It adds another layer of complexity, a new [API](https://github.com/lelandrichardson/redux-pack#using-the-handle-helper) to learn, on top of the already complex Redux.
* With redux-thunk every step of an async action becomes a dispatch, so they are part of the store history and are recorded.
* It still ends up in the same amount of store updates.
* [Testing](https://github.com/lelandrichardson/redux-pack#testing) becomes harder, compared to a traditional Redux or redux-thunk approach.

### 8.2.2. Other useful tools and approaches

As you can see, at least for me, the disadvantages outweigh the advantages. I think right now solutions like redux-thunk are necessary. But there are other tools, the will help you [reducing the boilerplate](https://redux.js.org/docs/recipes/ReducingBoilerplate.html), like [redux-bundler](https://github.com/henrikjoreteg/redux-bundler) and add nice functionality like [reselect](https://github.com/reactjs/reselect).

reselect lets you create [selectors](https://redux.js.org/docs/recipes/ComputingDerivedData.html) which give access to the values in teh store. Besides organizing the access to the store, you can create computed values, like filtered lists, which then would even be memoized, which means the value for that selector will be cached until any of it's sources, including other selectors, changes - awesome, isn't it?

redux-bundler goes a step further and gives you a convention on how to write reducer bundles, to reduce the amount of code to write. It uses reselect to provide selectors, has its own approach for [async actions: reactor](https://github.com/HenrikJoreteg/redux-bundler#what-about-async-stuff) and seems like a nice addition to the redux workflow.

In general you write a lot of code in Redux. Organizing and structuring it, can be quite challenging. One way to change that is using the [ducks](https://medium.com/@scbarrus/the-ducks-file-structure-for-redux-d63c41b7035c) pattern, and for bigger projects [re-ducks](https://medium.freecodecamp.org/scaling-your-redux-app-with-ducks-6115955638be). The bundles created by redux-bundler remind me a lot of the ducks pattern. In general it is a good idea to try to separate your root reducer into very small reducers. Should that not be possible, you could still use the re-ducks pattern to improve code organization.

### 8.2.3. Resources

* https://redux.js.org/docs/basics/
* https://redux.js.org/docs/recipes/ReducingBoilerplate.html
* https://redux.js.org/docs/recipes/ComputingDerivedData.html
* https://redux.js.org/docs/basics/ExampleTodoList.html
* https://www.valentinog.com/blog/react-redux-tutorial-beginners/
* https://auth0.com/blog/redux-practical-tutorial/
* https://www.youtube.com/watch?v=1w-oQ-i1XB8
* https://github.com/happypoulp/redux-tutorial
* https://github.com/markerikson/redux-ecosystem-links
* https://github.com/reactjs/redux/blob/master/docs/Glossary.md
* https://github.com/gaearon/redux-thunk
* https://thejsguy.com/2016/10/15/a-practical-introduction-to-es6-generator-functions.html
* https://redux-saga.js.org/docs/introduction/BeginnerTutorial.html
* http://blog.isquaredsoftware.com/2017/01/idiomatic-redux-thoughts-on-thunks-sagas-abstraction-and-reusability/
* https://medium.com/react-native-training/redux-4-ways-95a130da0cdc
* https://mobile.twitter.com/intelligibabble/status/800103510624727040
* https://stackoverflow.com/questions/35667249/accessing-redux-state-in-an-action-creator/35674575#35674575
* https://medium.com/@thisismissem/you-may-not-need-to-thunk-f5dc7a6fcbca
* https://decembersoft.com/posts/what-is-the-right-way-to-do-asynchronous-operations-in-redux/
* https://github.com/lelandrichardson/redux-pack
* https://www.reddit.com/r/reactjs/comments/5ic8kz/reduxpack_a_more_sensible_alternative_to_async/
https://stackoverflow.com/questions/39491517/how-to-use-redux-thunk-correctly-with-react/39492235#39492235
* https://github.com/reactjs/reselect
* https://github.com/henrikjoreteg/redux-bundler
* https://medium.com/@scbarrus/the-ducks-file-structure-for-redux-d63c41b7035c
* https://medium.freecodecamp.org/scaling-your-redux-app-with-ducks-6115955638be

## 8.3. Immutable State

### Resources

* https://facebook.github.io/immutable-js/
* https://github.com/mweststrate/immer

## 8.4. Alternatives

### 8.4.1. Resources

* https://medium.com/@machnicki/why-redux-is-not-so-easy-some-alternatives-24816d5ad22d

## 8.5. Conclusion

# 9. Code Conventions

## 9.1. Lint

## 9.2. Prettier

# 10. Testing