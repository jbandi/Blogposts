
---
tags: weekendreader, javascript, jobs
---

<img class="jb-main-img" property="og:image"  src="https://lh5.googleusercontent.com/-swZWub14X5c/VR7nUbDNBqI/AAAAAAAACJI/9Mg63bRhhsg/s800/WeekendReaderEaster.png" width="600px"/>

### [Scrum critics](http://gilesbowkett.blogspot.com.au/2014/09/why-scrum-should-basically-just-die-in.html)

Gilles Bowkett is quite provocative, but his points in [Why Scrum Should Basically Just Die In A Fire](http://gilesbowkett.blogspot.com.au/2014/09/why-scrum-should-basically-just-die-in.html) are interesting:

>Scrum covers up the inability to recruit (or even recognize) engineering talent, which is currently one of the most valuable things in the world, with a process for managing engineers as if they were cogs in a machine, all of equal value.

> "Velocity" is really too stupid to examine in much further detail, because it very obviously disregards this whole notion of "working software as a measure of progress" in favor of completely unreliable numbers based on almost nothing. 

> Scrum gives you demeaning rituals to dumb down your work so that people who will never understand it can pretend to understand it. Meanwhile, work which is genuinely difficult to track doesn't have to deal with this shit.

I don't think that these critics are all inherently valid for Scrum, but I think they are valid for most adoptions of Scrum today. James Shore has blogged about the [Decline and Fall of Agile](http://www.jamesshore.com/Blog/The-Decline-and-Fall-of-Agile.html) several years ago:

>These teams say they're Agile, but they're just planning (and replanning) frequently. Short cycles and the ability to re-plan are the benefit that Agile gives you. It's the reward, not the method. These psuedo-Agile teams are having dessert every night and skipping their vegetables.

### [The Salary of Programmers](http://www.quora.com/Since-programmers-on-average-produce-500-000*-for-the-tech-companies-they-work-for-why-arent-they-paid-more)

I find it hard to believe that there are "celebrity programmers" that make over $2 millon a year just for programming ... But the [Quora answers](http://www.quora.com/Since-programmers-on-average-produce-500-000*-for-the-tech-companies-they-work-for-why-arent-they-paid-more) have are some interesting discussions about what drives the salary of a job on the market.



### Anguar 2.0 is taking shape
The biggest news for me from [ng-conf 2015](https://www.youtube.com/playlist?list=PLOETEcp3DkCoNnlhE-7fovYvqwVPrRiY7) is that Angular 2 is developed in [TypeScript](http://www.typescriptlang.org/), and that the suggested way to develop Angular 2 apps will be to use TypeScript. I guess this finally motivates me to learn this language  ...
To get an overview of whats coming and the design and motivation behind Angular 2 I suggest watching the [Keynote from Misko Hevery](https://www.youtube.com/embed/-dMBcqwvYA0). Angular 2 makes a much cleaner impression, neatly designed around some consistent concepts, compared to the organically grown first version of Angular.
<iframe width="560" height="315" src="https://www.youtube.com/embed/-dMBcqwvYA0" frameborder="0" allowfullscreen></iframe>

### Wat? - Geek Humor
The [original WAT talk](https://www.destroyallsoftware.com/talks/wat) from Gary Bernhard is a classic. If you have not seen it, you should watch it now.

At ng-conf 2015 Shai Reznik did an adaption to Angular (the actual talk [starts at 4:20](https://youtu.be/M_Wp-2XA9ZU?t=4m21s)):
<iframe width="560" height="315" src="https://www.youtube.com/embed/M_Wp-2XA9ZU" frameborder="0" allowfullscreen></iframe>

###  [The workforce crisis](https://www.ted.com/talks/rainer_strack_the_surprising_workforce_crisis_of_2030_and_how_to_start_solving_it_now)
According to that prediction the future for companies looks not so bright,  the power-balance between workers and employers will shift. It will become a mayor issue for companies to attract and retain employees. As a freshly baked freelancer I think I should be happy about these predictions...

<iframe src="https://embed-ssl.ted.com/talks/rainer_strack_the_surprising_workforce_crisis_of_2030_and_how_to_start_solving_it_now.html" width="640" height="360" frameborder="0" scrolling="no" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

### [Frameworks as a recruiting investment](https://www.pandastrike.com/posts/20150311-react-bad-idea)
The article is primarily a rant about [React](https://facebook.github.io/react/) and how the design of React is bad and that it is basically an unnessecary framework. Instead on investing on "proprietary" frameworks, we should focus on technologies that make the web better as a whole.

But the rant contains an interesting theory: Angular and React are actually a recruiting investment for Google respective Facebook:

> So why release an open source Web framework at all? Because Facebook is battling Google for engineers. So you've got a big fight between two companies over which company is the coolest place to work, and both of them are companies that your grandparents love. How are you going to win this fight? One way is to have the hippest Web framework.

I find that theory very interesting, and it is one reasonable explanation why companies are investing in developing open-source frameworks.


### [Yet another Facebook framework](https://facebook.github.io/react/blog/2015/02/20/introducing-relay-and-graphql.html)
Speaking of companies releasing frameworks: After [React](https://facebook.github.io/react/) and [Flux](https://facebook.github.io/flux/) and the announcement of [React Native](http://www.reactnative.com/) the next announced open-source framework out of Facebook is [Relay](https://facebook.github.io/react/blog/2015/02/20/introducing-relay-and-graphql.html).
Relay is an interesting proposition how to solve a classical "mash-up" problem: UI-elements and backend are inherently coupled, since the UI-elements render data that is provided by the backend. In a "componentized" UI the UI-elements should be decoupled from each other, so it is easy to add or remove elements from the UI. However with the traditional separation between frontend and backend, each change in the UI composition leads to changes in the backend, since the UI needs different data. Relay and GraphQL tries to solve the problem with a generic server that can serve any data requests and a protocol that allows UI-elements to delclare what data they need. 
Looks intersting, however I am always afraid of generic solutions ...

### [Versioning is Hard](https://gist.github.com/jashkenas/cbd2b088e20279ae2c8e)
I have been in many projects, where there were endless discussions about versioning and there was never a really satisfactory solution. I am relieved that it seems that there really is no good solution as the [recent discussions](https://gist.github.com/jashkenas/cbd2b088e20279ae2c8e) about [semver](http://semver.org/) (semantic versioning) are showing:
<blockquote class="twitter-tweet" lang="en"><p>&quot;SemVer is a false promise that appeals to many developers&quot;, <a href="https://t.co/4qUW7qP57E">https://t.co/4qUW7qP57E</a> — <a href="https://twitter.com/jashkenas">@jashkenas</a> already said it better than I could.</p>&mdash; DHH (@dhh) <a href="https://twitter.com/dhh/status/550771282372227073">January 1, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>


### [Amazon vs. Google vs. Facebook vs. Apple](https://www.youtube.com/embed/XCvwCcEP74Q)
(via [fime's weekend reader](http://fime.ch/article/weekendreader2015-12.html))

An impresseive analysis of the leading four digital companies. A lot of information in 15 min, but if I understand the prediction correctly we should not bet on Amazon and Google...

<iframe width="560" height="315" src="https://www.youtube.com/embed/XCvwCcEP74Q" frameborder="0" allowfullscreen></iframe>

