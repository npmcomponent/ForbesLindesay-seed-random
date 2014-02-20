*This repository is a mirror of the [component](http://component.io) module [forbeslindesay/seed-random](http://github.com/forbeslindesay/seed-random). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/forbeslindesay-seed-random`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# seed-random

Generate random numbers with a seed, useful for reproducible tests


[![build status](https://secure.travis-ci.org/ForbesLindesay/seed-random.png?branch=master)](http://travis-ci.org/ForbesLindesay/seed-random)
[![Dependency Status](https://gemnasium.com/ForbesLindesay/seed-random.png)](https://gemnasium.com/ForbesLindesay/seed-random)
[![NPM version](https://badge.fury.io/js/seed-random.png)](http://badge.fury.io/js/seed-random)

## Installation

    $ npm install seed-random

## API

```javascript
var assert = require('assert');
var seed = require('../');

var trueRandomA = seed();
var trueRandomB = seed();
assert(trueRandomA() != trueRandomB());

var fakeRandomA = seed('foo');
var fakeRandomB = seed('foo');
assert(fakeRandomA() == fakeRandomB());

var fakeRandomC = seed('foo', {entropy: true});
var fakeRandomD = seed('foo', {entropy: true});
assert(fakeRandomC() != fakeRandomD());


seed('foo', {global: true});//over-ride global Math.random
var numA = Math.random();
seed('foo', {global: true});
var numB = Math.random();
assert(numA == numB);//always true

seed.resetGlobal();//reset to default Math.random
```

## License

MIT
