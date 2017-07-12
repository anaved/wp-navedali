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

[datacamp_exercise lang=&quot;python&quot;]
    [datacamp_pre_exercise_code]

    [/datacamp_pre_exercise_code]
    [datacamp_sample_code]
        class MyProperty(object):
            def __init__(self, name):
                self.__name = name

            @property
            def xname(self):
                return self.__name

            @xname.setter
            def xname(self, val):
                self.__name = val

            @xname.deleter
            def xname(self):
                del self.__name
    [/datacamp_sample_code]
    [datacamp_solution]

    [/datacamp_solution]
    [datacamp_sct]
        myProp = MyProperty(&quot;John&quot;)
        print myProp.xname
        myProp.xname = &quot;Doe&quot;
        print myProp.xname
        del myProp.xname
        print myProp.xname
    [/datacamp_sct]
    [datacamp_hint]

    [/datacamp_hint]
[/datacamp_exercise]

&nbsp;

Following are few flavors of properties.

&nbsp;
<ul>
 	<li><strong>Validation: </strong>Before setting a property value, we can perform any validation for data type, data range etc and throw an exception in case of failures.</li>
</ul>
&nbsp;
<ul>
 	<li>Before setting the internal property, you can validate that the provided value meets some criteria, and have it throw an error if it doesn't.</li>
</ul>
&nbsp;

&nbsp;
<ul>
 	<li>Lazy loading: Resources can by <a href="https://en.wikipedia.org/wiki/Lazy_loading" target="_blank" rel="nofollow noopener">lazily loaded</a> to defer work until it is actually needed, saving time and resources</li>
 	<li>Abstraction: Getters and setters allow you to abstract out the internal representation of data. Like our example above, for example, the first and last names are stored separately, but the getters and setters contain the logic that uses the first and last names to create the full name.</li>
 	<li>Debugging: Since mutator methods can encapsulate any code, it becomes a great place for interception when debugging (or logging) your code. For example, you could log or inspect each time that a property's value is changed.</li>
</ul>
Properties also allow creation of a final variable.

https://gist.github.com/anaved/9251ee318f9c43710993ddcf291daf2e.js