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
