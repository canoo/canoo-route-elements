# oo-route-elements

[![Travis Build](https://img.shields.io/travis/canoo/canoo-route-elements.svg)](https://travis-ci.org/canoo/canoo-route-elements)
[![MIT License](https://img.shields.io/badge/license-MIT%20License-blue.svg?style=flat)](https://opensource.org/licenses/MIT)
[![Polymer 2](https://img.shields.io/badge/webcomponents-Polymer%202-orange.svg?style=flat)](https://www.polymer-project.org/2.0/start/)
<!-- [![Canoo Incubator](https://img.shields.io/badge/canoo-incubator-be1432.svg?style=flat)](https://github.com/canoo) -->

~~~
$ bower install --save canoo/oo-route-elements
$ bower install --save PolymerElements/app-location
$ bower install --save PolymerElements/iron-pages
~~~

~~~html
<link rel="import" href="../app-route/app-location.html">
<link rel="import" href="../iron-pages/iron-pages.html">
<link rel="import" href="../oo-route-elements/oo-route.html">
<link rel="import" href="../oo-route-elements/oo-routes.html">

<app-location route="{{route}}" use-hash-as-path></app-location>

<oo-routes
    route="[[route.path]]"
    attr-for-selected="name"
    selected="{{routeName}}"
    params="{{routeParams}}">
  <oo-route name="foo" regexp pattern="/foo"></oo-route>
  <oo-route name="bar" regexp pattern="/bar"></oo-route>
  <oo-route name="baz" regexp pattern="/baz/(.+)"></oo-route>
</oo-routes>

<iron-pages
    attr-for-selected="name"
    selected="[[routeName]]">
  <div name="foo">foo</div>
  <div name="bar">bar</div>
  <div name="baz">baz</div>
</iron-pages>
~~~

## Usage

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
  <oo-route name="foo" regexp pattern="/foo"></oo-route>
  <oo-route name="bar" regexp pattern="/bar"></oo-route>
  <oo-route name="baz" regexp pattern="/baz/(.+)"></oo-route>
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
