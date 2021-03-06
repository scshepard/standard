# JavaScript Standard Style
[![travis][travis-image]][travis-url]
[![npm][npm-image]][npm-url]
[![downloads][downloads-image]][downloads-url]

[travis-image]: https://img.shields.io/travis/feross/standard.svg?style=flat
[travis-url]: https://travis-ci.org/feross/standard
[npm-image]: https://img.shields.io/npm/v/standard.svg?style=flat
[npm-url]: https://npmjs.org/package/standard
[downloads-image]: https://img.shields.io/npm/dm/standard.svg?style=flat
[downloads-url]: https://npmjs.org/package/standard

### One JavaScript style to rule them all

No decisions to make, no `.jshintrc` or `.jscs` files to manage. It just works.

## Install

```bash
npm install standard
```

## Rules

- **2 spaces** for indentation
- **Single quotes** for strings
  - Except to avoid escaping like `"in this lil' string"`
- **Unix line breaks** (LF)
- **No semicolons**
  - [It's totally fine.][1] *[Really!][2]*
- Never start a line with `(` or `[`:
  - This is the *one* gotcha with omitting semicolons – *automatically checked* for you!
  - Always prefix with `;` like this `;[1, 2, 3].join(' ')`
- Spaces after keywords:
  - `if (condition) { ... }`
- Spaces before/after function definitions:, like this:
  - `function name (arg1, arg2) { ... }`
- Always name the context variable `self`:
  - `var self = this`

[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons

To get a better idea, take a look at
[a sample file](https://github.com/feross/bittorrent-dht/blob/master/client.js) written
in JavaScript Standard Style.

## Usage

The easiest way to use `standard` is to install it globally as a Node command line
program. To do so, simply run the following command in your terminal (flag `-g` installs
`standard` globally on your system, omit it if you want to install in the current working
directory):

```bash
npm install standard -g
```

After you've done that you should be able to use the `standard` program. The simplest use
case would be checking the style of all JavaScript files in the current working directory:

```
$ standard
Error: Code style check failed:
  /Users/feross/code/webtorrent/lib/torrent.js:950:11: Expected '===' and instead saw '=='.
```

The `node_modules` and `.git` folders are automatically excluded when looking for `.js`
files to style check.

### What you might do if you're clever

1. Add it to `package.json`

  ```json
  {
    "name": "my-cool-package",
    "devDependencies": {
      "standard": "*"
    },
    "scripts": {
      "test": "standard && node my-normal-tests.js"
    }
  }
  ```

2. Check style automatically when you run `npm test`

  ```
  $ npm test
  Error: Code style check failed:
    /Users/feross/code/webtorrent/lib/torrent.js:950:11: Expected '===' and instead saw '=='.
  ```

3. Never give style feedback on a pull request again!

## License

MIT. Copyright (c) [Feross Aboukhadijeh](http://feross.org).
