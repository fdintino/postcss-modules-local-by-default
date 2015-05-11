[![Build Status][ci-img]][ci]

# PostCSS Local Scope

*This project is currently unpublished and not yet ready for production.*

[PostCSS] plugin to transform global selectors into the [local scope] format of [Webpack]'s [css-loader].

**WARNING: This project depends on [css-loader]'s [local scope] feature, which is marked as experimental and is very likely to change in the future.**

## Why?

Avoiding global scope in CSS is an amazing way to keep your styles clean.

Webpack allows this with [css-loader], but it's opt-in. This plugin is for those who want local scope to be the default, and global styles to be the exception.

## Syntax

```css
.foo { /* ... */ }

/* Break out of local scope when necessary */

:global(.global .selector) { /* ... */ }

:global .another .global .selector { /* ... */ }
```

```css
.local[foo] { /* ... */ }

.global .selector { /* ... */ }

.another .global .selector { /* ... */ }
```

## Usage

```js
postcss([ require('postcss-local-scope') ])
```

See [PostCSS] docs for examples for your environment.

[PostCSS]:     https://github.com/postcss/postcss
[ci-img]:      https://img.shields.io/travis/markdalgleish/postcss-local-scope/master.svg?style=flat-square
[ci]:          https://travis-ci.org/markdalgleish/postcss-local-scope
[Webpack]:     http://webpack.github.io
[css-loader]:  https://github.com/webpack/css-loader
[local scope]: https://github.com/webpack/css-loader#local-scope
