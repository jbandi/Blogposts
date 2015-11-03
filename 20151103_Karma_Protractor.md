---
tags: javascript, testing
---

For my [JavaScript / AngularJS workshops](http://www.ivorycode.com/#schulung) I created two illustrations to explain how unit-testing with Karma and end-to-end-testing with Protactor is working:

<img class="jb-main-img" property="og:image"  src="https://lh6.googleusercontent.com/-OljkzU3s2GA/VTLHyfZ_yYI/AAAAAAAACKk/rZuoy8AvE8Y/w1024-h768-no/Karma.jpg" width="600px"/>


<img class="jb-main-img" property="og:image"  src="https://lh6.googleusercontent.com/-57e_I3NlcRQ/VTLHygh_5_I/AAAAAAAACKo/kLsPoEw5CPI/w1024-h768-no/Protractor.jpg" width="600px"/>

In both setups the code is running in the browser. The main difference is, that with Karma I am testing isolated 'code-units' that are run individually, there is no complete running application involved.   
In the Protractor setup a complet running application has to be availabe and the test drives a browser to interact with this application.