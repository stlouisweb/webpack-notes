# Webpack Module Bundler
### Yet another build tool, that allows you to create modular components of your dependencies and load ni just the parts you need when you need them.

## [Quick intro to webpack](https://egghead.io/lessons/javascript-intro-to-webpack?__s=q7rjpmro69qqprqkvgoj)


Replace all script tags with a single script tag.

## Install webpack

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


## convert your scripts to modules

```javascript
var someModule = require('./someModule');
```

in someModule.js file:

```javascript
~~var someModule = {~~
  ...
}
```

```javascript
module.exports = {
  ...
}
```




