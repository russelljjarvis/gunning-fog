# gunning-fog [![Build Status][travis-badge]][travis] [![Coverage Status][codecov-badge]][codecov]

Formula to detect the grade level of text according to the
[Gunning fog index][formula].

See [syllable][] for detecting syllables.

## Installation

[npm][npm-install]:

```bash
npm install gunning-fog
```

## Usage

```js
var gunningFog = require('gunning-fog');

/* For “The Australian platypus is seemingly a hybrid of
 * a mammal and reptilian creature.” (1 sentence; 13 words;
 * 4 polysillabic words, of which two are jargon, proper nouns,
 * or compound words). */
gunningFog({
  sentence: 1,
  word: 13,
  complexPolysillabicWord: 2
});
// 11.353846...
```

## API

### `gunningFog(counts)`

Given an object containing the number of words (`word`), the
number of sentences (`sentence`), and the number of complex
(excluding jargon, proper nouns, compound words) polysillabic
(three or more syllables) words (`complexPolysillabicWord`)
in a document, returns the grade level associated with the
document.

## Related

*   [`automated-readability`](https://github.com/wooorm/automated-readability)
    — Uses character count instead of error-prone syllable parser
*   [`coleman-liau`](https://github.com/wooorm/coleman-liau)
    — Uses letter count instead of an error-prone syllable parser
*   [dale-chall-formula](https://github.com/wooorm/dale-chall-formula)
    — Uses a dictionary; suited for higher reading levels
*   [`flesch`](https://github.com/wooorm/flesch)
    — Uses syllable count
*   [flesch-kincaid](https://github.com/wooorm/flesch-kincaid)
    — Like **flesch**; returns U.S. grade levels
*   [`smog-formula`](https://github.com/wooorm/smog-formula)
    — Like `gunning-fog-index`; without needing advanced NLP
*   [`spache-formula`](https://github.com/wooorm/spache-formula)
    — Uses a dictionary; suited for lower reading levels

## License

[MIT][license] © [Titus Wormer][author]

<!-- Definitions -->

[travis-badge]: https://img.shields.io/travis/wooorm/gunning-fog.svg

[travis]: https://travis-ci.org/wooorm/gunning-fog

[codecov-badge]: https://img.shields.io/codecov/c/github/wooorm/gunning-fog.svg

[codecov]: https://codecov.io/github/wooorm/gunning-fog

[npm-install]: https://docs.npmjs.com/cli/install

[license]: LICENSE

[author]: http://wooorm.com

[formula]: http://en.wikipedia.org/wiki/Gunning_fog_index

[syllable]: https://github.com/wooorm/syllable
