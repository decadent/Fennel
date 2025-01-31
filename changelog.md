# Summary of user-visible changes

## 0.4.0 / ???

* ???

## 0.3.0 / 2019-09-22

This release introduces docstrings as well as several new features to
the macro system and some breaking changes; the most significant being
the new unquote syntax and the requirement of auto-gensym for
identifiers in backtick.

* Fix a bug where errors would show incorrect line numbers
* Add support for docstrings and `doc` for displaying them in repl
* Support `:detect-cycles? false` in fennelview to turn off "#<table 1>" output
* **Disallow** non-gensym identifiers in backtick/macros
* Support `x#` syntax for auto-gensym inside backtick
* Fix a bug in `lambda` arity checks when using destructuring
* Support `:one-line` output in fennelview
* Add `--require-as-include` to inline required modules in compiled output
* Add `--eval` argument to command-line launcher
* Add environment variable `FENNEL_PATH` to `path`.
* Fix a few bugs in `match`
* **Remove** undocumented support for single-quoted strings
* Add support for guard clauses with `?` in pattern matching
* Support completion in repl when `readline.lua` is available
* Add `--globals` and `--globals-only` options to launcher script
* **Remove** `luaexpr` and `luastatement` for a single `lua` special
* Improve code generation for `if` expressions in many situations
* Alias `#` special with `length`
* Replace `@` (unquote) with `,`; comma is **no longer** whitespace
* **Disallow** `~` in symbols other than `~=`
* Add `hashfn` and `#` reader macro for shorthand functions like `#(+ $1 $2)`
* Allow hashfn arguments to be used in multisyms
* Add `macro` to make defining a single macro easier
* Add `(comment)` special which emits a Lua comment in the generated source
* Allow lua-style method calls like `(foo:bar baz)`; **disallow** `:` in symbols

## 0.2.1 / 2019-01-22

This release mostly contains small bug fixes.

* Add `not=` as an alias for `~=`
* Fix a bug with `in-scope?` which caused `match` outer unification to fail
* Fix a bug with variadic `~=` comparisons
* Improve error reporting for mismatched delimiters

## 0.2.0 / 2019-01-17

The second minor release introduces backtick, making macro authoring
much more streamlined. Macros may now be defined in the same file, and
pattern matching is added.

* Prevent creation of bindings that collide with special forms and macros.
* Make parens around steps optional in arrow macros for single-arg calls
* Allow macros to be defined inline with `macros`
* Add `--add-package-path` and `--add-fennel-path` to launcher script
* Add `-?>` and `-?>>` macros
* Add support for quoting with backtick and unquoting with `@` (later changed to `,`)
* Support key/value tables when destructuring
* Add `match` macro for pattern matching
* Add optional GNU readline support for repl
* Fix a bug where runtime errors were not reported by launcher correctly
* Allow repl to recover gracefully from parse errors

## 0.1.1 / 2018-12-05

This release contains a few small bug fixes.

* Fix luarocks packaging so repl includes fennelview
* Fix bug in the repl where locals-saving would fail for certain input
* Fix launcher to write errors to stderr, not stdout

## 0.1.0 / 2018-11-29

The first real release sees the addition of several "creature comfort"
improvements such as comments, iterator support, line number tracking,
accidental global protection, pretty printing, and repl locals. It
also introduces the name "Fennel".

* Save locals in between chunks in the repl
* Allow destructuring in more places
* **Remove** redundant `defn` macro
* Add `doto` macro
* Support newlines in strings
* Prevent typos from accidentally referring to unknown globals
* Improve readability of compiler output
* Add `->` and `->>` macros
* **Remove** deprecated special forms: `pack`, `$`, `block`, `*break`, `special`
* Support nested lookup in `.` form
* Add `var`; disallow regular locals from being set
* Add `global`; refuse to set globals without it
* Make comparison operators variadic
* Support destructuring "rest" of a table into a local with `&`
* Add fennelview pretty-printer
* Add `require-macros`
* Add `//` for integer division on Lua 5.3+
* Add `fennel.dofile` and `fennel.searcher` for `require` support
* Track line numbers
* Add `partial`
* Add `local`
* Support binding against multiple values
* Add `:` for method calls
* Compile tail-calls properly
* Rename to Fennel
* Add `each`
* Add `lambda`/`λ` for arity-checked functions
* Add `when`
* Add comments

## 0.0.1 / 2016-08-14

The initial version (named "fnl") was created in 8 days and then
set aside for several years.
