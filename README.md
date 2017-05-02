# font-roboto-brick
An HTML import for Roboto using Brick

## Installation

### Bower

Just add it to your `bower.json` with:

```
bower i font-roboto-brick --save
```

## Vulcanization

To replace _font-roboto_ with _font-roboto-brick_ you need to ignore the first
one, since it's referenced by other (Polymer) components and reference the new
one yourself.

This is an example using gulp:

###### `gulpfile.js`

```javascript
var gulp = require('gulp');
var vulcanize = require('gulp-vulcanize');

gulp.task('vulcanize', function() {
  return gulp.src(baseDir + "/elements.html").pipe(vulcanize({
    abspath: '',
    excludes: [],
    stripExcludes: [baseDir + "/font-roboto/roboto.html"]
  })).pipe(gulp.dest(targetDir));
});
```

###### `elements.html`

```html
<!DOCTYPE html>

<meta charset='utf-8' />
<link rel="import" href="font-roboto-brick/roboto.html">
<link rel="import" href="paper-elements/paper-elements.html">
```
