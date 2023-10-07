<!--

@license Apache-2.0

Copyright (c) 2023 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# shape

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return the shape of a provided [ndarray][@stdlib/ndarray/base/ctor].

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import shape from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-shape@deno/mod.js';
```

#### shape( x, copy )

Returns the shape of a provided [ndarray][@stdlib/ndarray/base/ctor].

```javascript
import zeros from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-zeros@deno/mod.js';

var x = zeros( [ 3, 2, 3 ] );
// returns <ndarray>

var sh = shape( x, false );
// returns [ 3, 2, 3 ]
```

When `copy` is `false`, changes to the returned shape array may mutate the input [ndarray][@stdlib/ndarray/base/ctor] shape. If there is a chance that the returned shape will be mutated (either directly or by downstream consumers), set `copy` to `true` to prevent unintended side effects.

```javascript
import zeros from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-zeros@deno/mod.js';

var x = zeros( [ 3, 2, 3 ] );
// returns <ndarray>

var sh = shape( x, true );
// returns [ 3, 2, 3 ]

var bool = ( x.shape === sh );
// returns false
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

<!-- eslint-disable new-cap -->

```javascript
import zeros from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-zeros@deno/mod.js';
import slice from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-slice@deno/mod.js';
import E from 'https://cdn.jsdelivr.net/gh/stdlib-js/slice-multi@deno/mod.js';
import S from 'https://cdn.jsdelivr.net/gh/stdlib-js/slice-ctor@deno/mod.js';
import shape from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-shape@deno/mod.js';

// Create an array:
var x = zeros( [ 10, 10, 10, 10 ] );
// returns <ndarray>

// Define some slices:
var slices = [
    // :,:,:,:
    E( null, null, null, null ),

    // 5:10,4,2:4,::-1
    E( S( 5, 10 ), 4, S( 2, 4 ), S( null, null, -1 ) ),

    // :,:,2,:
    E( null, null, 2, null ),

    // 1,2,3,:
    E( 1, 2, 3, null ),

    // 1,3,::2,4::2
    E( 1, 3, S( null, null, 2 ), S( 4, null, 2 ) )
];

// Determine the shape of each slice...
var s;
var i;
for ( i = 0; i < slices.length; i++ ) {
    s = slice( x, slices[ i ] );
    console.log( 'slice(%s) => %s', x.shape.join( 'x' ), shape( s, false ).join( 'x' ) );
}
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-base-shape.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-base-shape

[test-image]: https://github.com/stdlib-js/ndarray-base-shape/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-base-shape/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-base-shape/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-base-shape?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-base-shape.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-base-shape/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-base-shape/tree/deno
[umd-url]: https://github.com/stdlib-js/ndarray-base-shape/tree/umd
[esm-url]: https://github.com/stdlib-js/ndarray-base-shape/tree/esm
[branches-url]: https://github.com/stdlib-js/ndarray-base-shape/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-base-shape/main/LICENSE

[@stdlib/ndarray/base/ctor]: https://github.com/stdlib-js/stdlib/tree/deno

</section>

<!-- /.links -->