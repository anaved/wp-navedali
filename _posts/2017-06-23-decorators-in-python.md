---
ID: 425
post_title: Decorators in Python
author: Naved
post_date: 2017-06-23 22:11:55
post_excerpt: ""
layout: post
permalink: >
  http://www.navedali.com/technology/python/decorators-in-python
published: true
dsq_needs_sync:
  - "1"
---
Decorators (@) in python are used to provide additional characteristic to a function. In other words a decorator wraps a function, modifying its behavior.

Few common usages of decorators are
<ul>
 	<li>@login_required: To validate if a user is logged in, otherwise load the login page</li>
 	<li>@memoize: To cache return value of a function based upon arguments</li>
 	<li>@patch: To monkey path a module or object members.</li>
</ul>
&nbsp;

Decorators with arguments

Memoize