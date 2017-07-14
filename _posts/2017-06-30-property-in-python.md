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
Properties in python are used to provide access methods to change an attribute of a class. By providing getter, setter, deleter methods, properties provide abstraction over the internal representation of the data. Property functions can range from data type validation, to any enrichment and calculation.

By adding a <code>@property</code> decorator, a method in python can be accessed like a variable. Any processing can be performed at the retrieval or at the setting of value. Sample of a class with a property.
https://gist.github.com/anaved/925df723a4c290392f6611bc707a1cb8
Following are few flavors of properties.
<h3>Validation In Property</h3>
Before setting a property value, we can perform any validation for data type, data range etc and throw an exception in case of failures.
https://gist.github.com/anaved/bdf3c3703f1050c10792dde4f8003ed1
<h3>Abstract Property</h3>
A property can also be declared abstract by using @abstractproperty decorator. This enforces the subclass to provide an implementation.
https://gist.github.com/anaved/5cd3ff493de65e5cd8dec74c00a4302e
<h3>Constant (Final ) Property</h3>
A property can be used to create constants in python. This can be achieved by returning a constant value from a getter, and not declaring a setter method.
https://gist.github.com/anaved/4728099bffd5ee642e2e95f4c4124ded
<h3>Declaring A Property Without Decorator</h3>
A property can also be created by declaring getter/setter methods and then passing them as argument to <code>property(...)</code>.
https://gist.github.com/3b43e62f55968fa537b6c4da2668ff3c