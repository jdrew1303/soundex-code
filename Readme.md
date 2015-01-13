# soundex-code [![Build Status](https://img.shields.io/travis/wooorm/soundex-code.svg?style=flat)](https://travis-ci.org/wooorm/soundex-code) [![Coverage Status](https://img.shields.io/coveralls/wooorm/soundex-code.svg?style=flat)](https://coveralls.io/r/wooorm/soundex-code?branch=master)

Fast [Soundex](http://en.wikipedia.org/wiki/Soundex) implementation. No cruft. Real fast.

Soundex is one of the earlier phonetics algorithms, specifically designed for surnames, inspiring others such as [metaphone](https://github.com/wooorm/metaphone).

Depending on your goals, additionally use a stemmer (e.g., my own porter stemmer [implementation](https://github.com/wooorm/stemmer)) for better results.

## Installation

npm:
```bash
$ npm install soundex-code
```

Component:
```bash
$ component install wooorm/soundex-code
```

Bower:
```bash
$ bower install soundex-code
```

## Usage

```js
var soundexCode = require('soundex-code');

soundexCode("phonetics"); // "P532"
soundexCode("Ashcraft"); // "A261"
soundexCode("Lissajous"); // "L222"
soundexCode("Smith") === soundex-code("Schmit"); // true

soundexCode("Ashcraftersson", 6); // "A26136"
soundexCode("A", 6); // "A000"
```

## CLI

Install:
```bash
$ npm install --global soundex-code
```

Use:
```
Usage: soundex-code [options] words...

Fast Soundex implementation

Options:

  -h, --help           output usage information
  -v, --version        output version number

Usage:

# output phonetics for words
$ soundex-code soundex unicorn
# S532 U526

# output phonetics for words from stdin
$ echo "soundex unicorn banana" | soundex-code
# S532 U526 B550
```

## Benchmark

On a MacBook Air, it runs about 516,000 op/s.

```
           soundexCode — this module
  410 op/s » op/s * 1,000

           natural
  182 op/s » op/s * 1,000

           soundex-encode
   45 op/s » op/s * 1,000

           soundex
   30 op/s » op/s * 1,000
```

## Related

- [metaphone](https://github.com/wooorm/metaphone) — The orignal Metaphone algorithm;
- [double-metaphone](https://github.com/wooorm/metaphone) — The Double Metaphone algorithm.

## License

MIT © Titus Wormer