<a href="https://pugasync.com"><img src="https://cdn.rawgit.com/semaphoreui/pugasync-logo/eec436cee8fd9d1726d7839cbe99d1f694692c0c/SVG/pug-final-logo-_-colour-128.svg" height="200" align="right"></a>

# PugAsync

Full documentation is at [pugasync.com](https://pugasync.com/)

Pug is a high-performance template engine implemented with JavaScript for [Node.js](http://nodejs.org) and browsers. For bug reports,
feature requests and questions, [open an issue](https://github.com/semaphoreui/pugasync/issues/new).

You can test drive Pug online [here](https://pugasync.com/).

## Packages

<!-- VERSION_TABLE -->
Package Name | Version
-------------|--------
pug | [![NPM version](https://img.shields.io/npm/v/pug?style=for-the-badge)](https://www.npmjs.com/package/pug)
pug-attrs | [![NPM version](https://img.shields.io/npm/v/pug-attrs?style=for-the-badge)](https://www.npmjs.com/package/pug-attrs)
pug-code-gen | [![NPM version](https://img.shields.io/npm/v/pug-code-gen?style=for-the-badge)](https://www.npmjs.com/package/pug-code-gen)
pug-error | [![NPM version](https://img.shields.io/npm/v/pug-error?style=for-the-badge)](https://www.npmjs.com/package/pug-error)
pug-filters | [![NPM version](https://img.shields.io/npm/v/pug-filters?style=for-the-badge)](https://www.npmjs.com/package/pug-filters)
pug-lexer | [![NPM version](https://img.shields.io/npm/v/pug-lexer?style=for-the-badge)](https://www.npmjs.com/package/pug-lexer)
pug-linker | [![NPM version](https://img.shields.io/npm/v/pug-linker?style=for-the-badge)](https://www.npmjs.com/package/pug-linker)
pug-load | [![NPM version](https://img.shields.io/npm/v/pug-load?style=for-the-badge)](https://www.npmjs.com/package/pug-load)
pug-parser | [![NPM version](https://img.shields.io/npm/v/pug-parser?style=for-the-badge)](https://www.npmjs.com/package/pug-parser)
pug-runtime | [![NPM version](https://img.shields.io/npm/v/pug-runtime?style=for-the-badge)](https://www.npmjs.com/package/pug-runtime)
pug-strip-comments | [![NPM version](https://img.shields.io/npm/v/pug-strip-comments?style=for-the-badge)](https://www.npmjs.com/package/pug-strip-comments)
pug-walk | [![NPM version](https://img.shields.io/npm/v/pug-walk?style=for-the-badge)](https://www.npmjs.com/package/pug-walk)
<!-- VERSION_TABLE -->

## Installation

### Package

To use Pug in your own JavaScript projects:

```bash
$ npm install pug
```

### Command Line

After installing the latest version of [Node.js](http://nodejs.org), install with:

```bash
$ npm install pug-cli -g
```

and run with

```bash
$ pug --help
```

## Syntax

Pug is a clean, whitespace sensitive syntax for writing HTML. Here is a simple example:

```pug
doctype html
html(lang="en")
  head
    title= pageTitle
    script(type='text/javascript').
      if (foo) bar(1 + 5);
  body
    h1 Pug - node template engine
    #container.col
      if youAreUsingPug
        p You are amazing
      else
        p Get on it!
      p.
        Pug is a terse and simple templating language with a
        strong focus on performance and powerful features.
```

Pug transforms the above to:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Pug</title>
    <script type="text/javascript">
      if (foo) bar(1 + 5);
    </script>
  </head>
  <body>
    <h1>Pug - node template engine</h1>
    <div id="container" class="col">
      <p>You are amazing</p>
      <p>
        Pug is a terse and simple templating language with a strong focus on
        performance and powerful features.
      </p>
    </div>
  </body>
</html>
```

## API

For full API, see [pugasync.com/api/reference.html](https://pugasync.com/api/reference.html)

```js
var pug = require('pug');

// compile
var fn = pug.compile('string of pug', options);
var html = fn(locals);

// render
var html = pug.render('string of pug', merge(options, locals));

// renderFile
var html = pug.renderFile('filename.pug', merge(options, locals));
```

### Options

- `filename` Used in exceptions, and required when using includes
- `compileDebug` When `false` no debug instrumentation is compiled
- `pretty` Add pretty-indentation whitespace to output _(`false` by default)_

## Browser Support

The latest version of pug can be [downloaded for the browser in standalone form](https://pugasync.com/js/pug.js). It only supports the very latest browsers, though, and is a large file. It is recommended that you pre-compile your pug templates to JavaScript.

To compile a template for use on the client using the command line, do:

```bash
$ pug --client --no-debug filename.pug
```

which will produce `filename.js` containing the compiled template.

## Tutorials

- cssdeck interactive [Pug syntax tutorial](http://cssdeck.com/labs/learning-the-jade-templating-engine-syntax)
- cssdeck interactive [Pug logic tutorial](http://cssdeck.com/labs/jade-templating-tutorial-codecast-part-2)
- [Pug について。](https://gist.github.com/japboy/5402844) (A Japanese Tutorial)

## Implementations in other languages

### Ports in other languages

Ports to other languages, with very close syntax:

- [PHP](https://github.com/pug-php/pug)
- [Java](https://github.com/neuland/jade4j)
- [Python](https://github.com/kakulukia/pypugjs)
- [Ruby](https://github.com/yivo/pug-ruby)
- [C# (ASP.NET Core)](https://github.com/AspNetMonsters/pugzor)
- [RPG/ILE](https://github.com/WorksOfLiam/apug)

### Equivalents in other languages

Templates engines for other languages with a different syntax, but a similar philosophy:

- [Scaml for Scala](https://scalate.github.io/scalate/documentation/scaml-reference.html)
- [Slim for Ruby](https://github.com/slim-template/slim) (should not be confused with Slim PHP framework)
- [HAML for Ruby](http://haml.info)

### Framework implementations/adapters

Embedded view engines for frameworks:

- [Laravel](https://github.com/BKWLD/laravel-pug)
- [Symfony](https://github.com/pug-php/pug-symfony)
- [Phalcon](https://github.com/pug-php/pug-phalcon)
- [CodeIgniter](https://github.com/pug-php/ci-pug-engine)
- [Yii 2](https://github.com/pug-php/pug-yii2)
- [Slim 3](https://github.com/pug-php/pug-slim)
- [Silex (implementation example)](https://gist.github.com/kylekatarnls/ba13e4361ab14f4ff5d2a5775eb0cc10)
- [Lumen](https://github.com/BKWLD/laravel-pug#use-in-lumen)
- [Rails](https://github.com/yivo/pug-rails)

### CMS plugins

- [WordPress](https://github.com/welaika/wordless)

## Additional Resources

- [Emacs Mode](https://github.com/brianc/jade-mode)
- [Vim Syntax](https://github.com/digitaltoad/vim-pug)
- [TextMate Bundle](http://github.com/miksago/jade-tmbundle)
- [Coda/SubEtha syntax Mode](https://github.com/aaronmccall/jade.mode)
- [html2pug](https://github.com/donpark/html2jade) converter
- [pug2php](https://github.com/SE7ENSKY/jade2php) converter
- [Pug Server](https://github.com/ctrlaltdev/pug-server) Ideal for building local prototypes apart from any application
- [cache-pug-templates](https://github.com/ladjs/cache-pug-templates) Cache Pug templates for [Lad](https://github.com/ladjs/lad)/[Koa](https://github.com/koajs/koa)/[Express](https://github.com/expressjs/express)/[Connect](https://github.com/senchalabs/connect) with [Redis](https://redis.io)
- [Prettier Plugin](https://github.com/prettier/plugin-pug)