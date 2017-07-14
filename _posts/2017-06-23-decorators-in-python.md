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
Following could be an example of a decorator which when used at declaration of a function, calls the same with a static argument, and returns the result

https://gist.github.com/anaved/90b5d05985da5b12eda9072abfccac70#file-simple_decorator-py

As you can observe, in the current format the decorator isn't of much use since the arguments to the decoratee function is fixed. Lets try if we can improve on that.

Lets try to write a memoized function. A simple implementation could be a <code>@memoize</code> decorator which stores the map of function input and output values. The decorator only calls the function if no records are found in the map, otherwise just return the results from the map. This kind of caching is useful when optimizing a heavy function.

https://gist.github.com/anaved/90b5d05985da5b12eda9072abfccac70#file-simple_decorator2-py

We can also use helper <code><a href="https://docs.python.org/2/library/functools.html#functools.wraps">@wraps</a></code> to give the impression that we are actually calling <em>adder by preserving its metadata </em><code>__name__</code>, <code>__doc__</code>, and <code>__module__</code>

https://gist.github.com/anaved/90b5d05985da5b12eda9072abfccac70#file-simple_decorator3-py

Since memoize function here is a callable object, lets try to implement the same using a class

&nbsp;

Things to keep in mind while writing decorators:
<ul>
 	<li>A proper decorator can also be called as ordinary function, without "@" signature</li>
 	<li>Always keep in mind to return value from the wrapper and also the underlying function</li>
 	<li>Always keep provision for  <code>*args, **kwargs</code> in all functions</li>
</ul>
Decorators with arguments

Implement Memoize decorator.

Decorator as class