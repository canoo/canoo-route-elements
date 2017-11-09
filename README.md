# canoo-route-elements

[![Travis Build](https://img.shields.io/travis/canoo/canoo-route-elements.svg)](https://travis-ci.org/canoo/canoo-route-elements)
[![Polymer 2](https://img.shields.io/badge/webcomponents-Polymer%202-orange.svg?style=flat)](https://www.polymer-project.org/2.0/start/)
[![MIT License](https://img.shields.io/badge/license-MIT%20License-blue.svg?style=flat)](https://opensource.org/licenses/MIT)
[![Canoo Incubator](https://img.shields.io/badge/canoo-incubator-be1432.svg?style=flat)](https://github.com/canoo)

~~~html
<app-location route="{{route}}" use-hash-as-path></app-location>

<canoo-routes
    route="[[route.path]]"
    attr-for-selected="name"
    selected="{{routeName}}"
    params="{{routeParams}}">
  <canoo-route name="foo" regexp pattern="/foo"></canoo-route>
  <canoo-route name="bar" regexp pattern="/bar"></canoo-route>
  <canoo-route name="baz" regexp pattern="/baz/(.+)"></canoo-route>
</canoo-routes>

<iron-pages
    attr-for-selected="name"
    selected="[[routeName]]">
  <div name="foo">foo</div>
  <div name="bar">bar</div>
  <div name="baz">baz</div>
</iron-pages>
~~~

Simple routes.

~~~html
<canoo-routes route="/bar">
  <canoo-route pattern="/foo"></canoo-route>
  <canoo-route pattern="/bar"></canoo-route>
</canoo-routes>
~~~

Routes with regular expression patterns.

~~~html
<canoo-routes attr-for-selected="name" route="/baz/quux">
  <canoo-route name="foo" regexp pattern="/foo"></canoo-route>
  <canoo-route name="bar" regexp pattern="/bar"></canoo-route>
  <canoo-route name="baz" regexp pattern="/baz/(.+)"></canoo-route>
</canoo-routes>
~~~

Routes with patterns.

~~~html
<canoo-routes attr-for-selected="name" route="/baz/quux">
  <canoo-route name="foo" pattern="/foo"></canoo-route>
  <canoo-route name="bar" pattern="/bar"></canoo-route>
  <canoo-route name="baz" pattern="/baz/:path"></canoo-route>
</canoo-routes>
~~~
