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

### Defining dependencies with CommonJs (sync require)
```javascript
require("module");
require("../file.js");
exports.doStuff = function() {};
module.exports = someVaule;
```
> A module can specify exports by adding properties to the exports object or setting the value of module.exports.

#### Pros
* Server-side modules can be reused
* There are already many modules in this style (npm)
* very simple and easy to use.
#### Cons
* blocking calls do not apply well on networks. Network requests are asynchronous.
* No parallel require of multiple modules.

### Defining dependencies with AMD (async require)
```javascript
require(["module", "../file"], function(module, file) {/* ... */});
define("mymodule", ["dep1", "dep2"], funciton(d1, d2) {
return some ExportedValue;
});
```
> AMD = Asynchronous Module Definition

#### Pros
* Fits to the asynchronous request style in networks.
* Parallel loading of multiple modules.

#### Cons
* Coding overhead. More difficult to read and write.
* Seems to be some kind of workaround.

---

You can also use ES6 same language consturcts and other styles of dependency definition.

---

### Transferring modules
Two standard methods of transfering modules are to either have 1 request per module or to send all modules in one request, both methods have flaws.

Webpack allows for chunked transferring of modules which splits the set of modules into multiple smaller batches (chunks).
Chuncks with modules that are not required initially are only requested on demand.

### [Why only javascript](http://webpack.github.io/docs/motivation.html#why-only-javascript)
Webpack allows the developer to modularize a whole range of assets besides just Javascript

## What is Webpack
> webpack is a module bundler.

> webpack takes modules with dependencies and generates static assets representing those modules.

#### Webpack goals
* Split the dependency tree into chunks loaded on demand
* Keep inital loading time low
* Every static asset should be able to be a module
* Ability to integrate 3rd-party libraries as modules
* Ability to customize nearly every part of the module bundler
* Suited for big projects

#### [Key features](http://webpack.github.io/docs/what-is-webpack.html#how-webpack-is-different)
* [Code Splitting](http://webpack.github.io/docs/code-splitting.html)
* [Loaders](http://webpack.github.io/docs/loaders.html)
* Clever parsing
* [Plugin System](http://webpack.github.io/docs/plugins.html)

## Installing Webpack
Install webpack globally via npm:

```
npm install webpack -g
```

Optionally you can add webpack as dependency to your project so that you can use a customized local version of webpack:

```
npm init
```

To add a package.json config file. then,

```
npm install webpack --save-dev
```

To Install webpack locally in your project. 


## [Usage](http://webpack.github.io/docs/usage.html)
Provides links to docs for CLI, node.js API and configuration options.

## Tutorial
[Official beginner tutorial](http://webpack.github.io/docs/tutorials/getting-started/)
