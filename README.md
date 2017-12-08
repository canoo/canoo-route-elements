# \<oo-routes\>

[![Travis Build](https://img.shields.io/travis/oolymer/oo-routes.svg)](https://travis-ci.org/oolymer/oo-routes)
[![MIT License](https://img.shields.io/badge/license-MIT%20License-blue.svg?style=flat)](https://opensource.org/licenses/MIT)
[![Polymer 2](https://img.shields.io/badge/webcomponents-Polymer%202-orange.svg?style=flat)](https://www.polymer-project.org/2.0/start/)
<!-- [![Canoo Incubator](https://img.shields.io/badge/canoo-incubator-be1432.svg?style=flat)](https://github.com/canoo) -->

**Table of Contents:**

<!-- TOC depthFrom:2 -->

- [Usage](#usage)
- [Examples](#examples)
- [Patterns](#patterns)
- [Semantic Versions](#semantic-versions)

<!-- /TOC -->

## Usage

~~~
$ bower install --save oolymer/oo-routes
$ bower install --save PolymerElements/app-location
$ bower install --save PolymerElements/iron-pages
~~~

~~~html
<link rel="import" href="../oo-routes/oo-route.html">
<link rel="import" href="../oo-routes/oo-routes.html">
<link rel="import" href="../app-route/app-location.html">
<link rel="import" href="../iron-pages/iron-pages.html">

<app-location route="{{route}}" use-hash-as-path></app-location>

<oo-routes
    route="[[route.path]]"
    attr-for-selected="name"
    selected="{{routeName}}"
    params="{{routeParams}}">
  <oo-route name="foo" use-regexp pattern="/foo"></oo-route>
  <oo-route name="bar" use-regexp pattern="/bar"></oo-route>
  <oo-route name="baz" use-regexp pattern="/baz/(.+)"></oo-route>
</oo-routes>

<iron-pages
    attr-for-selected="name"
    selected="[[routeName]]">
  <div name="foo">foo</div>
  <div name="bar">bar</div>
  <div name="baz">baz</div>
</iron-pages>
~~~

## Examples

Simple routes.

~~~html
<oo-routes route="/bar">
  <oo-route pattern="/foo"></oo-route>
  <oo-route pattern="/bar"></oo-route>
</oo-routes>
~~~

Routes with regular expression patterns.

~~~html
<oo-routes attr-for-selected="name" route="/baz/quux">
  <oo-route name="foo" use-regexp pattern="/foo"></oo-route>
  <oo-route name="bar" use-regexp pattern="/bar"></oo-route>
  <oo-route name="baz" use-regexp pattern="/baz/(.+)"></oo-route>
</oo-routes>
~~~

Routes with patterns.

~~~html
<oo-routes attr-for-selected="name" route="/baz/quux">
  <oo-route name="foo" pattern="/foo"></oo-route>
  <oo-route name="bar" pattern="/bar"></oo-route>
  <oo-route name="baz" pattern="/baz/:path"></oo-route>
</oo-routes>
~~~

## Patterns

>Every HTTP URL conforms to the syntax of a generic URI. A generic URI is of the form:
>
>~~~
>scheme:[//[user[:password]@]host[:port]][/path][?query][#fragment]
>~~~


Patterns | Route | Matched Route | Matched Params
---------|-------|---------------|----------------
`<oo-route name="foo" pattern="/foo">` <br> `<oo-route name="bar" pattern="/bar">` |  `{ path: "/foo" }` | foo | {}
`{ foo: "/foo", bar: "/bar" }` | `{ path: "/foo" }` | foo | {}
`{ foo: "/foo", bar: "/bar" }` | `{ path: "/bar" }` | bar | {}
`{ foo: "/foo", bar: "/bar" }` | `{ path: "/baz" }` | *none* | {}

## Semantic Versions

- Version number format `MAJOR.MINOR.PATCH`, e.g. "1.5.3".
- Increase MAJOR for breaking changes.
- Increase MINOR for new features.
- Increase PATCH for bug fixes.
