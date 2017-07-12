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

By adding a <strong>@property</strong> decorator, a method in python can be accessed like a variable. Any processing can be performed at the retrieval or at the setting of value. Sample of a class with a property.

https://gist.github.com/anaved/925df723a4c290392f6611bc707a1cb8

&nbsp;

Following are few flavors of properties.
<ul>
 	<li><strong>Validation: </strong>Before setting a property value, we can perform any validation for data type, data range etc and throw an exception in case of failures.</li>
</ul>
https://gist.github.com/anaved/bdf3c3703f1050c10792dde4f8003ed1
<ul>
 	<li><strong>Abstract Property: </strong> A property can also be declared abstract by using @abstractproperty decorator. This enforces the subclass to provide an implementation.</li>
</ul>
https://gist.github.com/anaved/5cd3ff493de65e5cd8dec74c00a4302e
<ul>
 	<li><strong>Constant (Final ) Property</strong>: A property can be used to create constants in python. This can be achieved by returning a constant value from a getter, and not declaring a setter method.</li>
</ul>
https://gist.github.com/anaved/4728099bffd5ee642e2e95f4c4124ded
<ul>
 	<li><strong>Declaring A Property Without Decorator: </strong>A property can also be created by declaring getter/setter methods and then passing them as argument to <strong>property(...).</strong></li>
</ul>
https://gist.github.com/3b43e62f55968fa537b6c4da2668ff3c

&nbsp;

&nbsp;