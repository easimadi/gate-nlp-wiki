```
=================================================
=====     jekyll-gulp-sass-browser-sync     =====
=================================================
```
A project including full setup for Jekyll, GulpJS, SASS, AutoPrefixer &amp; BrowserSync

## System Preparation

To use this project, you'll need the following things installed on your machine.

1. [Jekyll](http://jekyllrb.com/) - `$ gem install jekyll`
2. [Jekyll-Archives](http://jekyllrb.com) - `$ bundle install`
3. [NodeJS](http://nodejs.org) - use the installer.
4. [GulpJS](https://github.com/gulpjs/gulp) - `$ npm install -g gulp` (mac users may need sudo)

## Local Installation

1. Inside the directory, run `npm install`.
2. Enjoy

## Usage

**development mode**

This will give you file watching, browser synchronisation, auto-rebuild, CSS injecting etc etc.

```shell
$ gulp
```

**jekyll**

As this is just a Jekyll project, you can use any of the commands listed in their [docs](http://jekyllrb.com/docs/usage/)

## Deploy with Gulp

You can easily deploy your site build to a gh-pages branch. First, follow the instructions at [gulp-gh-pages](https://github.com/rowoot/gulp-gh-pages) to get your branch prepared for the deployment and to install the module. Then, in `gulpfile.js` you'll want to include something like the code below. `gulp.src()` needs to be the path to your final site folder, which by default will be `_site`. If you change the `destination` in your `_config.yml` file, be sure to reflect that in your gulpfile.



```javascript
var deploy = require("gulp-gh-pages");

gulp.task("deploy", ["jekyll-build"], function () {
    return gulp.src("./_site/**/*")
        .pipe(deploy());
});
```

# Basic use


## How to create a Topic:
You will create a file on `_article` directory. You must use the file extension `.md`.
``Note``, Topic is a parent article. Topic image put on the image directory.

Example for Topic file name:
```
example-topic.md
```
Example for Topic image:
```
exaple-topic1-image.jpg
```

## How to create Article:

Create a directory according to the topic name. Create a  ‘.md’ file on this directory. 
Example:
```
myarticle.md
myarticle-one.md
myarticle-2n.md
myarticle-another.md
```

Front Matter Templates:
Title, date, tag (required).
```
---
title: My article title
date:   2010-09-12 13:53:55 +0600
image: image.png
tag:
    - tag1
    - tag2
    - tag3
---
```

> Note:
  - Topic and Article name is better if you use the lowercase letter. Not use space.
  - Do not use space for Topic,  Article and image name. 
  - If the name of the topic and the name of the article's director is not the same, Articles can not be found on the website.  
