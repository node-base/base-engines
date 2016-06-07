# base-engines [![NPM version](https://img.shields.io/npm/v/base-engines.svg?style=flat)](https://www.npmjs.com/package/base-engines) [![NPM downloads](https://img.shields.io/npm/dm/base-engines.svg?style=flat)](https://npmjs.org/package/base-engines) [![Build Status](https://img.shields.io/travis/node-base/base-engines.svg?style=flat)](https://travis-ci.org/node-base/base-engines)

Adds support for managing template engines to your base application.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install base-engines --save
```

## Usage

Register the plugin with your [base](https://github.com/node-base/base) application:

```js
var Base = require('base');
var engines = require('base-engines');
base.use(engines());
```

## API

### [.engine](index.js#L45)

Register a view engine callback `fn` as `ext`. Calls `.setEngine` and `.getEngine` internally.

**Params**

* `exts` **{String|Array}**: String or array of file extensions.
* `fn` **{Function|Object}**: or `settings`
* `settings` **{Object}**: Optionally pass engine options as the last argument.

**Example**

```js
app.engine('hbs', require('engine-handlebars'));

// using consolidate.js
var engine = require('consolidate');
app.engine('jade', engine.jade);
app.engine('swig', engine.swig);

// get a registered engine
var swig = app.engine('swig');
```

### [.setEngine](index.js#L74)

Register engine `ext` with the given render `fn` and/or `settings`.

**Params**

* `ext` **{String}**: The engine to set.

**Example**

```js
app.setEngine('hbs', require('engine-handlebars'), {
  delims: ['<%', '%>']
});
```

### [.getEngine](index.js#L97)

Get registered engine `ext`.

**Params**

* `ext` **{String}**: The engine to get.

**Example**

```js
app.engine('hbs', require('engine-handlebars'));
var engine = app.getEngine('hbs');
```

## Related projects

You might also be interested in these projects:

* [base](https://www.npmjs.com/package/base): base is the foundation for creating modular, unit testable and highly pluggable node.js applications, starting… [more](https://github.com/node-base/base) | [homepage](https://github.com/node-base/base "base is the foundation for creating modular, unit testable and highly pluggable node.js applications, starting with a handful of common methods, like `set`, `get`, `del` and `use`.")
* [base-option](https://www.npmjs.com/package/base-option): Adds a few options methods to base, like `option`, `enable` and `disable`. See the readme… [more](https://github.com/node-base/base-option) | [homepage](https://github.com/node-base/base-option "Adds a few options methods to base, like `option`, `enable` and `disable`. See the readme for the full API.")
* [base-task](https://www.npmjs.com/package/base-task): base plugin that provides a very thin wrapper around [https://github.com/doowb/composer](https://github.com/doowb/composer) for adding task methods to… [more](https://github.com/node-base/base-task) | [homepage](https://github.com/node-base/base-task "base plugin that provides a very thin wrapper around <https://github.com/doowb/composer> for adding task methods to your application.")

## Contributing

This document was generated by [verb](https://github.com/verbose/verb), please don't edit directly. Any changes to the readme must be made in [.verb.md](.verb.md). See [Building Docs](#building-docs).

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/node-base/base-engines/issues/new).

## Building docs

Generate readme and API documentation with [verb](https://github.com/verbose/verb):

```sh
$ npm install -g verb verb-readme-generator && verb
```

## Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

## Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2016, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT license](https://github.com/node-base/base-engines/blob/master/LICENSE).

***

_This file was generated by [verb](https://github.com/verbose/verb), v0.9.0, on June 07, 2016._