# gulp-remarkable [![NPM version][npmjs-shields]][npmjs-url] [![Build Status][travis-img]][travis-url] [![Dependency Status][depstat-img]][depstat-url]
> [Gulp](http://gulpjs.com) plugin for [Remarkable][remarkable-url] - Markdown parser done right.  
Fast and easy to extend. Support [CommonMark][commonmark-url].

## Install [![Nodei.co stats][npmjs-install]][npmjs-url]
> Install with [npm](https://npmjs.org)

```
$ npm install gulp-remarkable
```


## Options
- `remarkableOptions` **{Object}** Options to be passed to Remarkable
- `typographer` **{Object}** Options to be passed to `md.typographer.set`.
  + to use it, first `remarkableOptions.typographer` must be set to `true`
- `preset` **{String}** Remarkable's preset, default `commonmark`


## Usage
**default example**
```js
var gulp = require('gulp'),
    name = require('gulp-rename'),
    md   = require('gulp-remarkable');

gulp.task('md', function() {
  return gulp.src('file.md')
    .pipe(md({preset: 'commonmark'}))
    .pipe(name('file.html'))
    .pipe(gulp.dest('dist'));
});

gulp.task('default', ['md']);
```

**extended example**
```js
var gulp = require('gulp'),
    name = require('gulp-rename'),
    md   = require('gulp-remarkable');

gulp.task('md', function() {
  return gulp.src('file.md')
    .pipe(md({
      preset: 'full',
      typographer: {
        copyright:    true, // (c) (C) → ©
        plusminus:    true, // +- → ±
        ellipsis:     true, // ... → … (also ?.... → ?.., !.... → !..)
      },
      remarkableOptions: {
        typographer: true,
        linkify: true,
        breaks: true
      }
    }))
    .pipe(name('file.html'))
    .pipe(gulp.dest('dist'));
});

gulp.task('default', ['md']);
```

## Run tests
```
$ npm test
```


## Authors & Contributors
**John Otander**
+ [github/johnotander][author-github]
+ [twitter/4lpine][author-twitter]
+ [npmjs/johno][author-npmjs]
+ [more ...][author-more]

**Charlike Mike Reagent** [![author tips][author2-gittip-img]][author2-gittip]
+ [gittip/tunnckoCore][author2-gittip]
+ [github/tunnckoCore][author2-github]
+ [twitter/tunnckoCore][author2-twitter]
+ [npmjs/tunnckoCore][author2-npmjs]
+ [more ...][author2-more]


## License [![MIT license][license-img]][license-url]
Copyright (c) 2014 [John Otander][author-website], [contributors](https://github.com/johnotander/gulp-remarkable/graphs/contributors).  
Released under the [`MIT`][license-url] license.



[downloads-img]: http://img.shields.io/npm/dm/gulp-remarkable.svg
[npm-required-version-img]: http://img.shields.io/badge/npm-%3E=%201.4.28-blue.svg
[node-required-version-img]: https://img.shields.io/node/v/gulp-remarkable.svg
[node-required-version-url]: http://nodejs.org/download/

[npmjs-url]: http://npm.im/gulp-remarkable
[npmjs-fury]: https://badge.fury.io/js/gulp-remarkable.svg
[npmjs-shields]: https://img.shields.io/npm/v/gulp-remarkable.svg
[npmjs-install]: https://nodei.co/npm/gulp-remarkable.svg?mini=true

[coveralls-url]: https://coveralls.io/r/johnotander/gulp-remarkable?branch=master
[coveralls-shields]: https://img.shields.io/coveralls/johnotander/gulp-remarkable.svg

[license-url]: https://github.com/johnotander/gulp-remarkable/blob/master/license.md
[license-img]: http://img.shields.io/badge/license-MIT-blue.svg

[travis-url]: https://travis-ci.org/johnotander/gulp-remarkable
[travis-img]: https://travis-ci.org/johnotander/gulp-remarkable.svg?branch=master

[depstat-url]: https://david-dm.org/johnotander/gulp-remarkable
[depstat-img]: https://david-dm.org/johnotander/gulp-remarkable.svg

[ferver-img]: http://img.shields.io/badge/using-ferver-585858.svg
[ferver-url]: https://github.com/jonathanong/ferver

[author-github]: https://github.com/johnotander
[author-twitter]: https://twitter.com/4lpine
[author-website]: http://johnotander.com
[author-npmjs]: https://npmjs.org/~johno
[author-more]: http://johnotander.com

[author2-gittip-img]: http://img.shields.io/gittip/tunnckoCore.svg
[author2-gittip]: https://www.gittip.com/tunnckoCore
[author2-github]: https://github.com/tunnckoCore
[author2-twitter]: https://twitter.com/tunnckoCore
[author2-website]: http://www.whistle-bg.tk
[author2-npmjs]: https://npmjs.org/~tunnckocore
[author2-more]: http://j.mp/1stW47C

[cobody-url]: https://github.com/tj/co-body
[mocha-url]: https://github.com/tj/mocha
[rawbody-url]: https://github.com/stream-utils/raw-body
[multer-url]: https://github.com/expressjs/multer
[express-url]: https://github.com/strongloop/express
[formidable-url]: https://github.com/felixge/node-formidable
[co-url]: https://github.com/tj/co
[extend-url]: https://github.com/justmoon/node-extend
[csp-report]: https://mathiasbynens.be/notes/csp-reports
[remarkable-url]: https://github.com/jonschlinkert/remarkable
[commonmark-url]: http://commonmark.org