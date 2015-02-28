thoughtpad-plugin-minifier-javascript
=================================

[![build status][travis-image]][travis-url]
[![Test coverage][coveralls-image]][coveralls-url]

A thoughtpad plugin that responds to Javascript post-compilation events. Javascript files will be minified for use in the browser.

## Usage

The plugin should be loaded using the [thoughtpad-plugin-manager](https://github.com/thoughtpad/thoughtpad-plugin-manager). Once this has been done then the plugin will respond to events. To use standalone:

```JavaScript
var man = require('thoughtpad-plugin-manager'),
    minify = require('thoughtpad-plugin-minifier-javascript');

var thoughtpad = man.registerPlugins([minify]);
thoughtpad.subscribe("javascript-postcompile-complete", function (data) {
    console.log("Minified javascript returned here"); 
});
thoughtpad.notify("javascript-postcompile-request", { contents: "your javascript code here" });
```

## Tests

Ensure you have globally installed mocha - `npm -g install mocha`. Then you can run:

`mocha`

Alternatively if you are in a *NIX environment `npm test` will run the tests plus coverage data.

## License

The code is available under the [MIT license](http://deif.mit-license.org/).

[travis-image]: https://img.shields.io/travis/thoughtpad/thoughtpad-plugin-minifier-javascript/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/thoughtpad/thoughtpad-plugin-minifier-javascript
[coveralls-image]: https://img.shields.io/coveralls/thoughtpad/thoughtpad-plugin-minifier-javascript/master.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/thoughtpad/thoughtpad-plugin-minifier-javascript?branch=master
