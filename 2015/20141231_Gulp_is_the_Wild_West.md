*TL;DR This post described how I implemented asset processing with Gulp in a .NET project.*

![enter image description here](https://lh5.googleusercontent.com/-FnAqNm21fBk/VKMvjm27SGI/AAAAAAAAB_U/CQTTn1cvw8o/s399/Gulp-Alive-Logo_1_1-7211401.jpg)

I am working on a .NET web application using [Nancy](http://nancyfx.org/) in the backend and [AngularJS](https://angularjs.org/) in the frontend.
I decided to use a frontend-build based on [Gulp](http://gulpjs.com/). Frontend builds based on [Grunt](http://gruntjs.com/) or [Gulp](http://gulpjs.com/) have a lot of momentum right now, and this seems a better option for me than some .NET based tools like [Cassette](http://getcassette.net/) or [SquishIt](https://github.com/jetheredge/SquishIt)

*By the way: if you have a node based frontend build you can run it on each Azure deployment like [described here](https://github.com/projectkudu/kudu/wiki/Deployment-hooks).*

My requirements were the following:

- For development the project should be runnable from VisualStudio without having to trigger a frontend build. That means that all the frontend assets have to be present at development time and referenced from my `.cshtml` files.
- For release the frontend assets should be processed (concatenated, minified, revisioned ...) by a frontend build. This build also needed to manipulate the `.cshtml` files, since they must reference the processed assets.

I started with [gulp-usemin](https://www.npmjs.com/package/gulp-usemin):

```
gulp.task("usemin", function() {
    return gulp.src("./Views/*.cshtml")
        .pipe(usemin({
            js: [ngAnnotate(), uglify(), rev()]
        }))
        .pipe(gulp.dest("Dist/"));

});
```
This was nice and easy and worked well ... until I had some more requirements ...

The problem:
With gulp-usemin you have not access to the stream in a pipeline. So you are limited to list some tasks that should be performed. If you want to do something more fancy, you are out of luck. In my case I wanted to add the output of angular template cache to my main js file after it has been concatenated and minified...
In my case I wanted to append another JavaScript file that contains my angular templates (generated with [gulp-angular-templatecache](https://www.npmjs.com/package/gulp-angular-templatecache))

So I started looking for another solution... thats where I discovered that I am in the Wild Wild West: [gulp-usemin2](https://www.npmjs.com/package/gulp-usemin2), [gulp-spa](https://www.npmjs.com/package/gulp-spa), [gulp-asset-transform](https://www.npmjs.com/package/gulp-asset-transform), [gulp-inject](https://www.npmjs.com/package/gulp-inject), [gulp-rev-replace](https://www.npmjs.com/package/gulp-rev-replace), [gulp-useref](https://www.npmjs.com/package/gulp-useref), [gulp-rev-all](https://www.npmjs.com/package/gulp-rev-all), [gulp-rev-collector](https://www.npmjs.com/package/gulp-rev-collector) ... all seem somehow to do something similar, documentation is minimalistic and you can waste a big amount of time to find the right plugin combination that works for you.

I ended up with the following combination of plugins:

```
var gulp = require("gulp");
var ngAnnotate = require("gulp-ng-annotate");
var templateCache = require("gulp-angular-templatecache");
var uglify = require("gulp-uglify");
var addsrc = require("gulp-add-src");
var concat = require("gulp-concat");
var rev = require("gulp-rev");
var minifyCSS = require("gulp-minify-css");
var useref = require("gulp-useref");
var filter = require("gulp-filter");
var revReplace = require("gulp-rev-replace");
var order = require("gulp-order");

gulp.task("angular-templates", function(){
    return gulp.src(TEMPLATES_SOURCES)
        .pipe(templateCache(TEMPLATES_JS, {module: "moonwalk", root: TEMPLATES_ROOT}))
        .pipe(gulp.dest("Temp/"));
});

gulp.task("release-assets", ["angular-templates"], function() {
    var assets = useref.assets();
    var jsFilter = filter("**/*.js");
    var moonwalkFilter = filter("**/" + MOONWALK_JS);
    var cssFilter = filter("**/*.css");

    return gulp.src("./Content/**/*.cshtml")
        .pipe(assets)               // Concatenate with gulp-useref
        .pipe(jsFilter)
        .pipe(ngAnnotate())         // Process javascript sources to add dependency injection annotations
        .pipe(uglify())             // Minify javascript sources
        .pipe(jsFilter.restore())
        .pipe(cssFilter)
        .pipe(minifyCSS())          // Minify CSS sources
        .pipe(cssFilter.restore())
        .pipe(moonwalkFilter)       // Filter the moonwalk.js source file, which is generated above by useref
        .pipe(addsrc("Temp/" + TEMPLATES_JS))// Add the templates.js to the stream, which is generated by a seperate task
        .pipe(order(["**/" + MOONWALK_JS, "*.js"]))// Order stream, so that templates.js is appended to moonwalk.js (needed, since templates depend on the angular module)
        .pipe(concat(MOONWALK_JS))// Concat the existing moonwalk.js and the templates.js into moonwalk.js
        .pipe(moonwalkFilter.restore())
        .pipe(rev())                // Rename the concatenated files
        .pipe(assets.restore())
        .pipe(useref())             // Replace the original references in the cshtml with the concatenated and processed resources by usemin
        .pipe(revReplace({replaceInExtensions:[".cshtml"]}))         // Replace the usemin generated resources with the reved resources
        .pipe(gulp.dest("Dist/"));
});
```


And by the way: This [thread about running tasks synchronously](https://github.com/gulpjs/gulp/issues/96) is representative for Gulp (final verdict: "This will be fixed in gulp 4") ... welcome in the wild wild west!