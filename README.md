# Webpack Module Bundler
### Yet another build tool, that allows you to create modular components of your dependencies and load in just the parts you need when you need them.

## [Quick intro to webpack](https://egghead.io/lessons/javascript-intro-to-webpack?__s=q7rjpmro69qqprqkvgoj)


Replace all script tags with a single script tag.

### Install webpack

```
npm install webpack
```

then create config file: webpack.config.js
config file exports the config

```javascript
module.exports = {
  entry: './index.js', // start of app
  output: {
    filename: 'bundle.js',
    path: __dirname
  }
};
```
command webpack runs config creates bundle.js.


### convert your scripts to modules

```javascript
var someModule = require('./someModule');
```

in someModule.js file:

replace

~~var someModule = {~~
  ...
}

with

module.exports = {
  ...
}


## [Why Webpack?](http://webpack.github.io/docs/motivation.html)
Because modern websites (webapps) are pushing more code over to the clientside. webpack creates a module system to help better organize your code.
Without webpack modularizing your code involves many script tags in your markup, which you then need to address how to load all these scripts.
> Modules export an interface to the global object, i. e. the window object. Modules can access the interface of dependencies over the global object.

There are some common problems with this approach:

* Conflicts in the global object.
* Order of loading is important.
* Developers have to resolve dependencies of modules/libraries.
* In big projects the list can get really long and difficult to manage.
