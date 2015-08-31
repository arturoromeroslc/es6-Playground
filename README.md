# ES6 Playground

# gulp-babel [![Build Status](https://travis-ci.org/babel/gulp-babel.svg?branch=master)](https://travis-ci.org/babel/gulp-babel)

> Turn ES6 code into vanilla ES5 with no runtime required using [babel](https://github.com/babel/babel)


## Install

```
$ npm install
$ gulp
```
### Inside of the es6 folder start coding with ES6 spec or with Javascript next... (ES7) 


## Usage

```js
var gulp = require('gulp');
var babel = require('gulp-babel');

gulp.task('default', function () {
  return gulp.src('src/app.js')
    .pipe(babel())
    .pipe(gulp.dest('dist'));
});
```

## API

`babel` [https://babeljs.io/docs/learn-es2015/]

### babel inside of Gulp task

```js
var gulp = require('gulp'),
    babel = require('gulp-babel'),
    plumber = require('gulp-plumber'),
    es6Path = 'es6/*.js',
    compilePath = 'es6/compiled';

gulp.task('babel', function () {
  gulp.src([es6Path])
      .pipe(plumber())
      .pipe(babel())
      .pipe(gulp.dest(compilePath + '/babel'));
});

gulp.task('watch', function() {
  gulp.watch([es6Path], ['babel'])
});

gulp.task('default', ['babel', 'watch']); 
```


#### Example ES6: 

```js
[1, 2, 3].map(n => n * 2);
// -> [ 2, 4, 6 ]

#### ES5 equivalent:

```js
[1, 2, 3].map(function(n) { return n * 2; }, this);
// -> [ 2, 4, 6 ]

