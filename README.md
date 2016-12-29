# ylru

[![NPM version][npm-image]][npm-url]
[![build status][travis-image]][travis-url]
[![Test coverage][codecov-image]][codecov-url]
[![David deps][david-image]][david-url]
[![Known Vulnerabilities][snyk-image]][snyk-url]
[![npm download][download-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/ylru.svg?style=flat-square
[npm-url]: https://npmjs.org/package/ylru
[travis-image]: https://img.shields.io/travis/node-modules/ylru.svg?style=flat-square
[travis-url]: https://travis-ci.org/node-modules/ylru
[codecov-image]: https://img.shields.io/codecov/c/github/node-modules/ylru.svg?style=flat-square
[codecov-url]: https://codecov.io/github/node-modules/ylru?branch=master
[david-image]: https://img.shields.io/david/node-modules/ylru.svg?style=flat-square
[david-url]: https://david-dm.org/node-modules/ylru
[snyk-image]: https://snyk.io/test/npm/ylru/badge.svg?style=flat-square
[snyk-url]: https://snyk.io/test/npm/ylru
[download-image]: https://img.shields.io/npm/dm/ylru.svg?style=flat-square
[download-url]: https://npmjs.org/package/ylru

**hashlru inspired**

[hashlru](https://github.com/dominictarr/hashlru) is the **Simpler, faster LRU cache algorithm.**
Please checkout [algorithm](https://github.com/dominictarr/hashlru#algorithm) and [complexity](https://github.com/dominictarr/hashlru#complexity) on hashlru.

ylru extends some features base on hashlru:

- cache value can be **expired**.
- cache value can be **empty value**, e.g.: `null`, `undefined`, `''`, `0`

## Usage

```js
const LRU = require('ylru');

const lru = new LRU(100);
lru.set(key, value);
lru.get(key);

// value2 will be expired after 5000ms
lru.set(key2, value2, { maxAge: 5000 });
lru.get(key2);
```

### API

## LRU(max) => lru

initialize a lru object.

### lru.get(key) => value | null

Returns the value in the cache.

### lru.set(key, value[, options])

- `{Number} options.maxAge`: value will become `undefined` after `maxAge` pass.
If `maxAge` not set, value will be never expired.

Set the value for key.

## License

[MIT](LICENSE)
