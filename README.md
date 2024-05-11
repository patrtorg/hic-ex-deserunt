# @patrtorg/hic-ex-deserunt <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

ES2015-compliant shim for Object.is - differentiates between -0 and +0, and can compare to NaN.

Essentially, Object.is returns the same value as === - but true for NaN, and false for -0 and +0.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.es/ecma262).

## Example

```js
Object.is = require('@patrtorg/hic-ex-deserunt');
var assert = require('assert');

assert.ok(Object.is());
assert.ok(Object.is(undefined));
assert.ok(Object.is(undefined, undefined));
assert.ok(Object.is(null, null));
assert.ok(Object.is(true, true));
assert.ok(Object.is(false, false));
assert.ok(Object.is('foo', 'foo'));

var arr = [1, 2];
assert.ok(Object.is(arr, arr));
assert.equal(Object.is(arr, [1, 2]), false);

assert.ok(Object.is(0, 0));
assert.ok(Object.is(-0, -0));
assert.equal(Object.is(0, -0), false);

assert.ok(Object.is(NaN, NaN));
assert.ok(Object.is(Infinity, Infinity));
assert.ok(Object.is(-Infinity, -Infinity));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@patrtorg/hic-ex-deserunt
[npm-version-svg]: https://versionbadg.es/es-shims/@patrtorg/hic-ex-deserunt.svg
[deps-svg]: https://david-dm.org/es-shims/@patrtorg/hic-ex-deserunt.svg
[deps-url]: https://david-dm.org/es-shims/@patrtorg/hic-ex-deserunt
[dev-deps-svg]: https://david-dm.org/es-shims/@patrtorg/hic-ex-deserunt/dev-status.svg
[dev-deps-url]: https://david-dm.org/es-shims/@patrtorg/hic-ex-deserunt#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@patrtorg/hic-ex-deserunt.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@patrtorg/hic-ex-deserunt.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@patrtorg/hic-ex-deserunt.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@patrtorg/hic-ex-deserunt
[codecov-image]: https://codecov.io/gh/es-shims/@patrtorg/hic-ex-deserunt/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/es-shims/@patrtorg/hic-ex-deserunt/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/es-shims/@patrtorg/hic-ex-deserunt
[actions-url]: https://github.com/patrtorg/hic-ex-deserunt/actions
