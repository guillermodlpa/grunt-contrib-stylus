# Options

## compress
Type: `Boolean`  
Default: `true`

Specifies if we should compress the compiled css. Compression is always disabled when `--debug` flag is passed to grunt.

## linenos
Type: `Boolean`  
Default: `false`

Specifies if the generated CSS file should contain comments indicating the corresponding stylus line.

## firebug
Type: `Boolean`  
Default: `false`

Specifies if the generated CSS file should contain debug info that can be used by the FireStylus Firebug plugin.

## paths
Type: `Array`

Specifies directories to scan for `@import` directives when parsing.

## define
Type: `Object`

Allows you to define global variables in Gruntfile that will be accessible in Stylus files.

## rawDefine
Type: `Boolean|Array|String`

If set to `true`, defines global variables in Gruntfile without casting objects to Stylus lists. Allows using a JavaScript object in Gruntfile to be accessible as a Stylus Hash. See Stylus's issue tracker for details. [stylus/stylus#1286](https://github.com/stylus/stylus/issues/1286)

Allows passing an array or string to specify individual keys to define "raw", casting all other keys as default Stylus behavior.

## urlfunc
Type: `String|Object`

If `String`: specifies function name that should be used for embedding images as Data URI.

If `Object`:
* `name` - Type: `String`. Function name that should be used for embedding images as Data URI.
* [ `limit` ] - Type: `Number|Boolean` Default: `30000`. Bytesize limit defaulting to 30Kb (30000), use false to disable the limit.
* [ `[paths` ] - Type: `Array`, Default: `[]`. Image resolution path(s).

See [url()](http://stylus.github.io/stylus/docs/functions.url.html) for details.


## [use](https://github.com/stylus/stylus/blob/master/docs/js.md#usefn)
Type: `Array`

Allows passing of stylus plugins to be used during compile.

## [import](https://github.com/stylus/stylus/blob/master/docs/js.md#importpath)
Type: `Array`

Import given stylus packages into every compiled `.styl` file, as if you wrote `@import '...'`
in every single one of said files.

## include css
Type: `Boolean`  
Default: `false`

When including a css file in your app.styl by using `@import "style.css"`, by default it will not include the full script, use `true` to compile into one script.
( **NOTICE:** the object key contains a space `"include css"` )

## [resolve url](http://stylus.github.io/stylus/docs/executable.html#resolving-relative-urls-inside-imports)
Type: `Boolean`  
Default: `false`

Telling Stylus to generate `url("bar/baz.png")` in the compiled CSS files accordingly from `@import "bar/bar.styl"` and `url("baz.png")`, which makes relative pathes work in Stylus.

_All urls are resolved relatively to position of resulting `.css` file_

( **NOTICE:** the object key contains a space `"resolve url"` and Stylus resolves the url only if it finds the provided file )

## resolve url nocheck
Type: `Boolean`  
Default: `false`

Like [resolve url](#resolve-url), but without file existence check. Fixing [some current issues](https://github.com/stylus/stylus/issues/2119).

( **NOTICE:** the object key contains two spaces `"resolve url nocheck"` )

## banner
Type: `String`  
Default: `''`

This string will be prepended to the beginning of the compiled output.

## relativeDest
Type: `String`  
Default: `''`

Path to be joined and resolved with each file dest to get new one. Mostly useful for files specified using wildcards:

```js
options: {
  relativeDest: 'out'
},
files: [{
  src: ['src/components/*/*.styl'],
  ext: '.css'
}]
```

will generate `src/components/*/out/*.css` files.
