react-project-setup v1
======================

This repository aims to collect resources, opinions and conclusions surrounding react related topics, to provide a guideline for setting up react projects and to provide an example implementation.

<!-- TOC -->

- [1. Language](#1-language)
    - [1.1. ES6 (ECMAScript 2015)](#11-es6-ecmascript-2015)
        - [1.1.1. Resources](#111-resources)
    - [1.2. Babel](#12-babel)
        - [1.2.1. Resources](#121-resources)
    - [1.3. Static Typing](#13-static-typing)
        - [1.3.1. Resources](#131-resources)
    - [1.4. Typescript](#14-typescript)
        - [1.4.1. Resources](#141-resources)
- [2. Build process](#2-build-process)
    - [2.1. Webpack](#21-webpack)
    - [2.2. gulp](#22-gulp)
    - [2.3. Conclusion](#23-conclusion)
- [3. create-react-app](#3-create-react-app)
    - [3.1. Resources](#31-resources)
- [4. Styling](#4-styling)
    - [4.1. CSS Modules](#41-css-modules)
    - [4.2. SCSS](#42-scss)
    - [4.3. Conclusion](#43-conclusion)
- [5. State Management](#5-state-management)
    - [5.1. Redux](#51-redux)
    - [5.2. Alternatives](#52-alternatives)
    - [5.3. Conclusion](#53-conclusion)
- [6. Testing & Code Conventions](#6-testing--code-conventions)
    - [6.1. Lint](#61-lint)
    - [6.2. Prettier](#62-prettier)
- [7. npm vs. yarn](#7-npm-vs-yarn)

<!-- /TOC -->

# 1. Language

## 1.1. ES6 (ECMAScript 2015)

Really? Do you doubt using ES6 makes sense? [Here](http://blog.thefirehoseproject.com/posts/12-reasons-es6-future-javascript-web-development/) is a tiny introduction to new features of ES6 and [here](http://es6-features.org/) you find a whole list of cool, sparkly things you can do with JavaScript. We can even go further and check out features from ES7 and ES8 - more about that in the Babel section. The current state of ECMAScripts' development can be found [here](https://github.com/tc39).

### 1.1.1. Resources

* http://blog.thefirehoseproject.com/posts/12-reasons-es6-future-javascript-web-development/
* https://tech.io/playgrounds/6439/modern-es6-javascript-pt--1
* http://es6-features.org/
* https://github.com/tc39

## 1.2. Babel

So we want to use the features of ES 6, 7 and 8, right? Do you remember the days when the same code produced different results in Firefox, Chrome and the Inter Explorer? That still happens as we know, but thanks to [Babel](https://babeljs.io/) and other frameworks and polyfills, this is not a major headache anymore, at least not compared to the situation a few years ago. Of course not all the cool shiny features are implemented in the browsers yet. This is were [Babel](https://babeljs.io/#es2015-and-beyond) shines, it [transpiles](https://scotch.io/tutorials/javascript-transpilers-what-they-are-why-we-need-them) ES 6+ Code down to ES 5 Code, so it can be used in all the browsers.

Because Babel has been around since forever, from a JavaScript frontend developers perspective, you can find a ton of resources of how to use it and there are so many [projects](https://babeljs.io/users/) using it, it really is [everywhere](https://babeljs.io/docs/setup/). You usually don't have to learn how to use the [Babel CLI](https://babeljs.io/docs/setup/#installation) but rather setup Babel being used in a Webpack workflow - more on that in the Webpack section.

### 1.2.1. Resources

* https://babeljs.io/
* https://scotch.io/tutorials/javascript-transpilers-what-they-are-why-we-need-them

## 1.3. Static Typing

Do we need type checking in JS? The short answer: [yes](https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007#1a07), the long one: [yes, but only for bigger projects](https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007#f51a). Also take a look [here](https://stackify.com/typescript-vs-javascript-migrate/) - scroll down to "When To Choose: TypeScript vs. JavaScript". 

Right now there two competitors - actually there are many more if you consider languages that have totally different syntax and eco system as JavaScript (e.g. [Elm](http://elm-lang.org/)). If you want to stay with JavaScript [TypeScript](https://www.typescriptlang.org/) and [Flow](https://flow.org/) are the most popular options. While both tools have their [advantages](https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007#b560), it seems that TypeScript is gaining more and more ground in the [comparison](https://github.com/niieani/typescript-vs-flowtype). Also check out this [discussion on TypeScript vs. Flow](https://www.reddit.com/r/javascript/comments/7bfwpl/flow_vs_typescript/).

With version 2 of Googles Framework [AngularJS](https://angularjs.org/), the team decided to fully work [on top of TypeScript](https://vsavkin.com/writing-angular-2-in-typescript-1fa77c78d8e8). That's another game changer favouring TypeScript over Flow.

For bigger applications, complicated logic, big teams, or regularly changing team members, static typing your JavaScript code makes total sense and almost seems mandatory today. For a small private project, with just one contributor it seems unnecessary. Right now, for me, the go to choice is TypeScript. It seems to be faster, better maintained, you get typings for (almost) all the frameworks out there and have an excellent IDE integration.

### 1.3.1. Resources

* https://codeburst.io/strict-types-typescript-flow-javascript-to-be-or-not-to-be-959d2d20c007
* https://blog.mariusschulz.com/2017/01/13/typescript-vs-flow
* https://www.reddit.com/r/javascript/comments/7bfwpl/flow_vs_typescript/
* https://github.com/niieani/typescript-vs-flowtype
* https://vsavkin.com/writing-angular-2-in-typescript-1fa77c78d8e8
* https://stackify.com/typescript-vs-javascript-migrate/

## 1.4. Typescript

So now that we decided to use TypeScript, how do we actually use it? It can be quite painful to refactor a complete code base, but there is a [guide](https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide) written by the TypeScript team. You would prefer starting with a clean slate, where the [examples](https://www.typescriptlang.org/samples/index.html) of TypeScript setups would help you. [Here](https://github.com/Microsoft/TypeScript-Babel-Starter/blob/master/README.md) is [one](https://github.com/Microsoft/TypeScript-Babel-Starter/blob/master/README.md) that helps you getting started with TypeScript and the still in pre-release existing [Babel 7](https://medium.com/@jdolle/babel-7-beta-instructions-aed5cf17048b) compiler. Babel 7 will be quite huge for TypeScript projects, because so far you needed to use the TypeScript compiler as an extra step, before using Babel. Now, Babel 7 can compile TypeScript directly. If you add React to the equation, there is even an easier way to setup your project, using [create-react-app](https://github.com/facebook/create-react-app) with a special [TypeScript script](https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter) - more about [create-react-app](https://github.com/facebook/create-react-app) in it's section.

### 1.4.1. Resources

* https://www.typescriptlang.org/samples/index.html
* https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide
* https://medium.com/@jdolle/babel-7-beta-instructions-aed5cf17048b
* http://artsy.github.io/blog/2017/11/27/Babel-7-and-TypeScript/
* https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter

# 2. Build process

## 2.1. Webpack

## 2.2. gulp

## 2.3. Conclusion

# 3. create-react-app

[create-react-app](https://github.com/facebook/create-react-app) is really practical it creates react apps with no build configuration. Meaning all the webpack tweaks, seting up a dev server etc. are taken care of - isn't that [awesome](https://medium.com/@tuchk4/why-i-love-create-react-app-e63b1be689a3)? The idea is that the scripts of create-react-app take care of all the configuration files and the basic folder structure. As long as you don't need something very specific or crazy, you should be fine staying with create-react-app.

There are additional scripts that boost the functionality of the create-react-scripts, for example one for [TypeScript support](https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter). You can even create your [own custom create-react-app template](https://auth0.com/blog/how-to-configure-create-react-app/).

Once you reach the point where the ready made template isn't doing it for you anymore, you [eject](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#npm-run-eject) create-react-app and all the managed configuration files will be available and you will be no longer using create-react-app. **This operation can not be undone!**

Even though there was a [plugin system](https://github.com/facebook/create-react-app/issues/670) discussed, it doesn't seem like they are going to work on that right now. But it seems like there might be an [alternative](https://neutrino.js.org/): [Neutrino](https://neutrino.js.org/) - I will check that out soon.

Try to stay as long as possible with create-react-app. It keeps the project clean and abstracts build process configuration and are usually more or less the same anyway. Another benefit, create-react-app will take care of updating their scripts, which means you only have to update create-react-app to receive webpack, babel etc. updates.

## 3.1. Resources

* https://github.com/facebook/create-react-app
* https://medium.com/@tuchk4/why-i-love-create-react-app-e63b1be689a3
* https://hackernoon.com/simple-react-development-in-2017-113bd563691f
* https://www.fullstackreact.com/p/using-webpack-with-create-react-app/
* https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md
* https://github.com/Microsoft/TypeScript-React-Starter#typescript-react-starter
* https://auth0.com/blog/how-to-configure-create-react-app/
* https://neutrino.js.org/

# 4. Styling

## 4.1. CSS Modules

## 4.2. SCSS

## 4.3. Conclusion

# 5. State Management

## 5.1. Redux

## 5.2. Alternatives

## 5.3. Conclusion

# 6. Testing & Code Conventions

## 6.1. Lint

## 6.2. Prettier

# 7. npm vs. yarn