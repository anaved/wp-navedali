---
ID: 425
post_title: Decorators in Python
author: Naved
post_excerpt: ""
layout: post
permalink: >
  http://www.navedali.com/technology/python/decorators-in-python
published: true
post_date: 2017-06-23 22:11:55
---
Decorators or Wrappers (@) in python are used to provide additional characteristic to a function. In other words a decorator wraps a function, modifying its behavior.

These are simply other python functions which return functions as return values.

Few common usages of decorators are
<ul>
 	<li><code>@login_required</code>: To validate if a user is logged in, otherwise load the login page</li>
 	<li><code>@memoize</code>: To cache return value of a function based upon arguments</li>
 	<li><code>@patch</code>: To monkey patch a module or object members.</li>
</ul>
A simple decorator memoize could be a function which stores the map of function input and output values. The decorator only calls the function if no records are found in the map, otherwise just return the results from the map. This kind of caching is useful when optimizing a heavy function.

https://gist.github.com/anaved/5262a6c761f675805955823ad6ff6b88

Things to keep in mind while writing decorators:
<ul>
 	<li>A proper decorator can also be called as ordinary function, without "@" signature</li>
 	<li>Always keep in mind to return value from the wrapper and also the underlying function</li>
 	<li>Always keep provision for  <code>*args, **kwargs</code> in all functions</li>
</ul>
Decorators with arguments

Implement Memoize decorator.