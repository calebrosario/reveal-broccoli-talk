##  Chainable Examples

```
/* global require, module */

var mergeTrees = require('broccoli-merge-trees');
var pickFiles  = require('broccoli-static-compiler');
var EmberApp   = require('ember-cli/lib/broccoli/ember-app');
var app        = new EmberApp({
    name: require('./package.json').name
});

app.import('bower_components/modernizr/modernizr.js');
app.import('bower_components/jquery/dist/jquery.js');
app.import('bower_components/jPushMenu/css/jPushMenu.css');
app.import('bower_components/jPushMenu/js/jPushMenu.js');
app.import('bower_components/moment/moment.js');


app.import({
  development : 'bower_components/respond/dest/respond.src.js',
  production  : 'bower_components/respond/dest/respond.min.js'
});

app.import({
  development : 'bower_components/bootstrap/dist/js/bootstrap.js',
  production  : 'bower_components/bootstrap/dist/js/bootstrap.min.js'
});

app.import({
  development : 'bower_components/bootstrap/dist/css/bootstrap.css',
  production  : 'bower_components/bootstrap/dist/css/bootstrap.min.css'
});

var fontAssets = pickFiles('bower_components/font-awesome', {
   srcDir: '/',
   files: ['**/*.woff', '**/*.ttf', '**/*.svg', '**/*.eot'],
   destDir: '/'
});

var fontEntypo = pickFiles('bower_components/entypo/font', {
  srcDir: '/',
  files: ['**/*.eot', '**/*.svg', '**/*.ttf', '**/*.woff', '**/*.css'],
  destDir: '/fonts'
});

var bootstrapMap = pickFiles('bower_components/bootstrap/dist/css', {
  srcDir: '/',
  files: ['**/*.map'],
  destDir: '/assets'
});

module.exports = mergeTrees([app.toTree(), fontAssets, fontEntypo, bootstrapMap]);
```
