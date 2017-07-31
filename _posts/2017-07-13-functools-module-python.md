---
ID: 465
post_title: functools Module In Python
author: Naved
post_excerpt: ""
layout: post
permalink: >
  http://www.navedali.com/technology/python/functools-module-python
published: true
post_date: 2017-07-13 16:21:42
---
As per python docs "<em>The <a class="reference internal" title="functools: Higher-order functions and operations on callable objects." href="https://docs.python.org/2/library/functools.html#module-functools" target="_blank" rel="noopener"><code class="xref py py-mod docutils literal"><span class="pre">functools</span></code></a> module is for higher-order functions: functions that act on or return other functions.</em>"
<h3>Partial</h3>
Star of <code>functools</code>is certainly partial, which provides ability to set a subset of arguments expected by a function. This partially set function can now be passed to the next consumer to provide rest of the arguments and finally invoke the function. Objects returned by <code>partial</code> are instances of <code>Partial</code>, and can further be chained if we desire to provide few more arguments but not want to invoke the function yet.