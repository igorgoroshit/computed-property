# computed-property [![NPM version](https://badge.fury.io/js/computed-property.svg)](http://badge.fury.io/js/computed-property)

> Add computed properties to JavaScript objects.

## Install
## Install with [npm](npmjs.org)

```bash
npm i computed-property --save
```

## Run tests

```bash
npm test
```

## Usage

```js
var computedProperty = require('computed-property');
```

## API
### [.computedProperty](index.js#L50)

Add a computed property to an object. This updates the property when dependent properties are updated.

* `obj` **{Object}**: Object to add the property to.
* `property` **{String}**: Name of the property.
* `dependencies` **{Array}**: Optional list of properties to depend on.
* `getter` **{Function}**: Getter function that does the calculation.

```js
var computedProperty = require('computed-property');
var file = {
  name: 'home-page',
  ext: '.hbs',
  dirname: 'views',
  data: {
    title: 'Home'
  }
};

computedProperty(
  // object
  file,
  // property name
  'path',
  // optional dependencies (may be deeply nested)
  ['name', 'ext', 'dirname', 'data.title'],
  // getter function
  function () {
    return this.dirname + '/' + this.name + this.ext;
  });
```


## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/doowb/computed-property/issues)

## Author

**Brian Woodward**

+ [github/doowb](https://github.com/doowb)
+ [twitter/doowb](http://twitter.com/doowb)

## License
Copyright (c) 2014 Brian Woodward
Released under the MIT license

***

_This file was generated by [verb](https://github.com/assemble/verb) on December 12, 2014._
