# canoo-route-elements

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
