---
tags: javascript, react, angularjs
---
<img class="jb-main-img" property="og:image"  src="https://lh3.googleusercontent.com/-jNo-2rEITGQ/VhgIaAWZaPI/AAAAAAAACag/yc1d2kVh1Yw/s912-Ic42/ReactAngular.jpg" />


I am currently working for a team that is about to build a web frontend for their in-house legacy system. The web frontend is basically a greenfield project, and the team can freely choose their technology stack.

I developed a small technology prototype in [AngularJS](https://angularjs.org/) and [React](https://facebook.github.io/react/). For both solutions I used npm and [webpack](https://webpack.github.io/) as a build environement. In the AngularJS solution I used [TypeScript](http://www.typescriptlang.org/) and in the React solution I used [ES2015](http://www.ecma-international.org/ecma-262/6.0/) (formerly ES6) and [Babel](https://babeljs.io/).

The prototype is here: https://bitbucket.org/jonasbandi/webshop/

I presented both solutions to the team, and let them decide which stack they like to choose for the actual project.

The team decided that they felt more comfortable with the solution based on React.

There were two main reasons:

- AngularJS is currently in a strange state, since Angular 2.0 is announced and hyped but not ready for production yet. If you start a project based on AngularJS now, you get the feeling that you are writing in a legacy technology right from the beginning.
- The React solution left a conciser impression and was clearer to grasp by the team. For example to realize a "component" in AngularJS you have to understand Directives (a DDO is pretty arcane for a newbie) and the implementation is spread over several entities (DDO, Controller, template ...). In contrast to that the approach of React to components is much easier to grasp.

This decision was made some weeks ago. In the meantime I set up the real project with the following components:

- A Build based on npm, [webpack](https://webpack.github.io/), [Babel](https://babeljs.io/) and [ESLint](http://eslint.org/) (no gulp or grunt)
- [React](https://facebook.github.io/react/) 0.14 / [ReactRouter](https://github.com/rackt/react-router) 1.0
- Flux Architecture based on [Alt.js](http://alt.js.org/)
- Internationalization with [i18next](http://i18next.com/)

