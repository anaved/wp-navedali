---
ID: 435
post_title: Properties In Python
author: Naved
post_excerpt: ""
layout: post
permalink: >
  http://www.navedali.com/technology/python/property-in-python
published: true
post_date: 2017-06-30 20:50:15
---
Properties in python are used to get/set attributes, and obfuscate various functionalities performed at the writing and reading of data.

These functions can range from data type validation to any enrichment and calculation.

Put simply properties allow functions to be presented as variables.
<ul>
 	<li>Validation: Before setting the internal property, you can validate that the provided value meets some criteria, and have it throw an error if it doesn't.</li>
 	<li>Lazy loading: Resources can by <a href="https://en.wikipedia.org/wiki/Lazy_loading" target="_blank" rel="nofollow noopener">lazily loaded</a> to defer work until it is actually needed, saving time and resources</li>
 	<li>Abstraction: Getters and setters allow you to abstract out the internal representation of data. Like our example above, for example, the first and last names are stored separately, but the getters and setters contain the logic that uses the first and last names to create the full name.</li>
 	<li>Debugging: Since mutator methods can encapsulate any code, it becomes a great place for interception when debugging (or logging) your code. For example, you could log or inspect each time that a property's value is changed.</li>
</ul>
Properties also allow creation of a final variable.