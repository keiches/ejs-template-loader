# EJS Template to string loader for Webpack

> EJS loader for [webpack](http://webpack.github.io/). Uses [ejs](https://github.com/mde/ejs) function to compile templates.

To use EJS by mde use 2.x branch and 2.x.x versions.

*** __Forked from [ejs-file-loader](https://github.com/pinkahd/ejs-loader.git)__ ***

## Installation

`npm install --save-dev ejs-template-loader`

### Usage

``` javascript
var template = require("ejs-template-loader!./file.ejt");
// => returns the template function compiled with ejs templating engine.

// And then use it somewhere in your code
template(data) // Pass object with data

// Child Templates
// path is relative to where webpack is being run
<%- include templates/child -%>
```

## Documentation

[Documentation: Using loaders](http://webpack.github.io/docs/using-loaders.html)

Following options can be specified in query:

`beautify` — enable or disable uglify-js beautify of template ast

`compileDebug` — see ejs compileDebug option

`htmlmin` — see [htmlminify section](#htmlminify)

## Examples for html minify

```javascript
const webpackConfigs = {
  module: {
    loaders: [
      {test: /\.ejs$/, loader: 'ejs-file-loader?htmlmin'} // enable here
    ]
  },
  'ejs-template-loader': {
    'htmlmin': true, // or enable here
    'htmlminOptions': {
      removeComments: true
    }
  }
};
```

See [all options reference](https://github.com/kangax/html-minifier#options-quick-reference)

## License

[MIT](http://www.opensource.org/licenses/mit-license.php)



