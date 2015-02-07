---
tags: weekendreader, javascript
---

<img class="jb-main-img" property="og:image"  src="https://lh4.googleusercontent.com/-bD7GC_7dwQY/VNU_jfP1q-I/AAAAAAAACGY/U6l1Mbq8qZw/s800/WR201506_2.png" width="600px"/>

### Agile Critics
The current state of agile is critizised by some more prominent figures:
Martin Fowler: [Not Just Code Monkeys](https://www.youtube.com/watch?v=4E3xfR6IBII)

> Developers should not just be passive receivers of product backlog items. This is where most Agile transitions fail.

<iframe width="560" height="315" src="https://www.youtube.com/embed/4E3xfR6IBII" frameborder="0" allowfullscreen></iframe>
<br/>
Dave Thomas: [The Death of Agile](http://www.thoughtworks.com/talks/the-death-of-agile)
The first ten minutes are hilarious, where Dave is mocking the commercialisation of Scrum in the past and the new trend of selling "Enterprise Agile".
<iframe class="wistia_embed" name="wistia_embed" src="http://fast.wistia.net/embed/iframe/vxwuanffvp?canonicalUrl=http%3A%2F%2Fwww.thoughtworks.com%2Ftalks%2Fthe-death-of-agile&canonicalTitle=The%20Death%20of%20Agile%20%7C%20ThoughtWorks" allowtransparency="true" frameborder="0" scrolling="no" width="480" height="298"></iframe>

### Facebook announces React Native
With [React Native](http://www.reactnative.com/) Facebook invented yet another approach to program mobile applications in JavaScript. They promise to combine the best of native apps and the web. As far as I understood they use native components  of iOS/Android (no HTML, no browser, no WebView), but they wrap them in JavaScript/JSX and use the JavaScript runtime on iOS/Android to orchestrate the application including the rendering. A very interesting approach ...
However they are not chasing the **"pipe dream of write once - run everywhere"**. You will write apps dedicated for iOS or Android, however the programming environment will be the same. They call it **"learn once, write anywhere"**.

<iframe width="560" height="315" src="https://www.youtube.com/embed/KVZ-P-ZI6W4" frameborder="0" allowfullscreen></iframe>
On a side note, the [React Native presentation](https://www.youtube.com/watch?v=KVZ-P-ZI6W4) comes with a strong statement in favour of native app development and against web/hybrid mobile apps. 

### Yet Another JavaScript Framework with big Ambitions
[<img class="jb-main-img" property="og:image"  src="https://lh5.googleusercontent.com/-HpUktrXaTLg/VNUtJgHJPJI/AAAAAAAACFQ/QUBboQrekyE/s185/main-logo.png" />](http://aurelia.io/index.html)
[Aurelia](http://aurelia.io/index.html) is a next generation JavaScript client framework, created by [Rob Eisenberg](http://eisenbergeffect.bluespire.com/), the creator of Durandal. Rob was for a short time part of the Angular team, but he changed his mind and [decided to go his own way](http://eisenbergeffect.bluespire.com/leaving-angular/) ... the result is a modern framework that builds on ES6 and WebComponents. Sounds interesting, but sceptics might say:
[<img class="jb-main-img" property="og:image"  src="https://lh3.googleusercontent.com/-NvQIqViYq9A/VNUv9y4WoJI/AAAAAAAACFk/x15NFspE3x8/s490/xusNCWe.jpg" width="300px"/>](http://www.reddit.com/r/ProgrammerHumor/comments/2tuj7e/my_reaction_to_aureliajs/)

### The JavaScript ecosystem is broken
In the interesting article [Generation Javascript](http://manuel.bernhardt.io/2014/12/30/generation-javascript/) the desolate state of the JavaScript ecosystem is revealed.

> Not every week-end project should be made public and available through Bower. The Javascript community needs to learn to filter itself.

<blockquote class="twitter-tweet" lang="en"><p>Being a JavaScript developer in 2014 is like speed dating.&#10;&#10;45 seconds with each framework before you have to re-write.</p>&mdash; I Am Devloper (@iamdevloper) <a href="https://twitter.com/iamdevloper/status/544815596932968448">December 16, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

In the same direction goes: [Why we should stop using Grunt & Gulp](http://blog.keithcirkel.co.uk/why-we-should-stop-using-grunt/) or my own post: [Gulp is the Wild West](http://blog.jonasbandi.net/2014/12/gulp-is-wild-west.html)

### Client Side Templating: Good or Bad?
There has been some recent discussion about client side templating (like it is done by most modern JavaScript frameworks like Angular, Ember and also React):

The challenge was 
- [The problem with Angular](http://www.quirksmode.org/blog/archives/2015/01/the_problem_wit.html) 
- [Angular and templating](http://www.quirksmode.org/blog/archives/2015/01/angular_and_tem.html)

It reminded me of a debate from some years ago: 
- [Progressive Enhancement is Dead](http://tomdale.net/2013/09/progressive-enhancement-is-dead/)  
- [Progressive Enhancement: Still Not Dead](http://thatemil.com/blog/2013/07/02/progressive-enhancement-still-not-dead/), 
- [Progressive enhancement is faster](http://jakearchibald.com/2013/progressive-enhancement-is-faster/)

This time there was a very interesting reaction: 
- [Experimentally verified: "Why client-side templating is wrong"](http://www.onebigfluke.com/2015/01/experimentally-verified-why-client-side.html) . 
I like the conclusion that is backed up by data: **For typical (line of business) web applications the advantages of the client-side rendering approach outweight the disadvantages by far**. For public facing sites, where displaying initial content matters and functionality is only a second aspect, client-side rendering can be slower and optimizations with server-side rendering can be worth the effort.



### You should start looking into ES6
ES6 will bring a lot of changes. JavaScript codebases will not look the same once ES6 catches on. Features like the [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [template string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings) and especially [generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*) will change the face of JavaScript substantially.

The following videos give a good introduction to what is coming in ES6.

[ES6 the future is now](https://www.youtube.com/watch?v=Hjkc9m9vYCU):
<iframe width="420" height="315" src="https://www.youtube.com/embed/Hjkc9m9vYCU" frameborder="0" allowfullscreen></iframe>

<br/>
[Netflix JavaScript Talks - Version 7: The Evolution of JavaScript](https://www.youtube.com/watch?v=DqMFX91ToLw):
<iframe width="560" height="315" src="https://www.youtube.com/embed/DqMFX91ToLw" frameborder="0" allowfullscreen></iframe>
<br/>
To get started quickly with using ES6 now, this is a good tutorial: [Javascript in 2015](https://www.youtube.com/watch?v=iukBMY4apvI)
<iframe width="420" height="315" src="https://www.youtube.com/embed/iukBMY4apvI" frameborder="0" allowfullscreen></iframe>

###Learning Promises
Promises in JavaScript are not the easiest concept to grasp. However due to the asynchronous nature of JavaScript  they are a very important concept, that can and should have a major impact on the architecture and structure of JavaScript applications. I learned a lot from the following presentation: [Promise-Based Architecture](https://www.youtube.com/watch?v=uUj-J3oUmOw)

<iframe width="560" height="315" src="https://www.youtube.com/embed/uUj-J3oUmOw" frameborder="0" allowfullscreen></iframe>