# generator-gulp-angular-less

Offers you a Yeoman generator to initiate a Web application with the following workflow:

<img height="100" align="left" src="media/bullet-yo.gif">

<img height="100" align="left" src="media/gulp.png">

<img height="100" align="left" src="media/bower-logo.png">

<img height="100" align="left" src="media/angularjs-logo.png">

<img height="100" align="left" src="media/less.png">

<br><br><br><br>

## Why fork?

Added `less` support and remove bootstrap/foundation UI options.

## Why generator-gulp-angular-less ?

This generator combines the best features of other generators like [generator-angular](https://github.com/yeoman/generator-angular), [ngTailor](https://github.com/lauterry/generator-ngtailor) and [generator-gulp-webapp](https://github.com/yeoman/generator-gulp-webapp) into an optimal workflow for starting applications with AngularJS powered by Gulp!

generator-gulp-angular scaffolds an AngularJS application with a full-featured gulpfile.js, giving you immediate out-of-the-box access to all tasks for modern web development.

My intention is to create a generator that gives users total control over their development toolbox so they can immediately start projects with their preferred tools, such as specific UI frameworks or JavaScript preprocessors.

## Usage

### Create your project

Install the required tools: `yo`, `gulp`, `bower`
```
npm install -g yo gulp bower
```

Install `generator-gulp-angular`:
```
npm install -g generator-gulp-angular
```

Make a new directory, and `cd` into it:
```
mkdir my-new-project && cd $_
```

Run `yo gulp-angular`, optionally passing an app name:
```
yo gulp-angular [app-name]
```

### Use Gulp tasks

* `gulp` or `gulp build` to build an optimized version of your application in `/dist`
* `gulp serve` to launch a browser sync server on your source files
* `gulp serve:dist` to launch a server on your optimized application
* `gulp wiredep` to fill bower dependencies in your `.html` file(s)
* `gulp test` to launch your unit tests with Karma
* `gulp protractor` to launch your e2e tests with Protractor
* `gulp protractor:dist` to launch your e2e tests with Protractor on the dist files

## Directory structure

[Best Practice Recommendations for Angular App Structure](https://docs.google.com/document/d/1XXMvReO8-Awi1EZXAXS4PzDzdNvV6pGcuaF4Q9821Es/pub)

But I recommend keeping to a division by file type: scripts, styles, partials.

## Features included in the gulpfile
* *useref* : allow configuration of your files in comments of your HTML file
* *ngMin* : convert simple injection to complete syntax to be minification proof
* *uglify* : optimize all your JavaScript
* *csso* : optimize all your CSS
* *rev* : add a hash in the file names to prevent browser cache problems
* *watch* : watch your source files and recompile them automatically
* *jshint* : JavaScript code linter
* *imagemin* : all your images will be optimized at build
* *Unit test (karma)* : out of the box unit test configuration with karma
* *e2e test (protractor)* : out of the box e2e test configuration with protractor
* *browser sync* : full-featured development web server with livereload and devices sync
* *ngHtml2js* : all HTML partials will be converted to JS to be bundled in the application
* **TODO** lazy : don't process files which haven't changed when possible

## Questions the generator will ask
* *jQuery*: jQuery 1.x, 2.x, Zepto, none
* *Angular modules*: animate, cookies, touch, sanitize
* *Resource handler*: ngResource, Restangular, none
* *Router*: ngRoute, UI Router, none

## Known issue

Protractor tests are not stable with PhantomJS, at least not on my Mac. I'm getting unpredictable disconnections between webdriverjs and phantomjs.

I tried many configurations for Protractor without success, any hint would be appreciated.

## Changelog

### 0.5.0

* Fork project
* Remove `sass` support
* Remove `bootstrap` and `foundation` ui options

### 0.4.0

* New welcome page presenting integrated technologies
* Several package updates: `yosay`, `browsersync`, `modernizr`, `protractor`...
* Some bug fixes: #6, #7, #8
* Add some documentation

### 0.3.1

* Fix e2e tests to use BrowserSync as server. But no way to stop BrowserSync for now so the task never really ends.

### 0.3.0

* Integration of BrowserSync as development server in place of a home made connect server
* Serve task is the entry point and launch the watch task

### 0.2.1

* Fix main.html missing with routing
* Fix unit tests by ignoring bootstrap js files in wiredep

### 0.2.0

* Convert HTML templates into JS and add them into the optimized bundle
* Let you choose to use jQuery, Zepto or nothing (Angular's jqLite)
* Ask for optional Angular modules: animate cookies, touch and sanitize
* Resource handler: ngResource, Restangular, none.
* Router: ngRoute, UI Router, none.

### 0.1.1

* Adding Travis CI

### 0.1.0

* Add unit test with karma and e2e test with protractor
* Split gulp configuration in multiple files
* Create 'inception' test which generate files and try gulp tasks on it
* Add ability to serve dist files and run e2e test on dist files
* Still no options

### 0.0.1

* Initial commit
* Scaffolds a working directory but with no options and no tests

## License

MIT
