---
ID: 666
post_title: Context Managers In Python
author: Naved
post_excerpt: ""
layout: post
permalink: >
  http://www.navedali.com/technology/python/context-managers-python
published: true
post_date: 2017-07-24 09:28:36
---
<span></span><span></span><span></span>Context managers are inherent feature of python to provide a way to obtain and release resources on demand.
<span></span><span></span><span></span> When a context manager is used, a definite scope is defined to safely delete or clean resources.
<span></span><span></span><span></span> For example a file can be read in below two ways.
https://gist.github.com/anaved/437ed10fa2c2a4f3252e715aa2f2b006#file-file_read_in_context-py
<ol>
 	<li><span></span><span></span><span></span>In this method, python interpreter has no way to estimate the need for myFile in future. Hence it holds on to the file descriptor until the program scope.</li>
 	<li><span></span><span></span><span></span>This method of file access ensures a clear scope of the usage of the resource file test.txt. This file is closed at the end of the block, and any file descriptor associated is released. This cleanup is performed behind the scenes as an effect of opening he file in a context.</li>
</ol>
<span></span><span></span>To achieve such behavior a class must define below two methods.
<ol>
 	<li><span></span><span></span> &lt;code&gt;__enter__&lt;/code&gt; : called at the time of entering the context, initialises resources. Return value shall be the handle to the object we want to pass for further operation within the block. Most common is to to return self here.</li>
 	<li><span></span><span></span> &lt;code&gt;__exit__&lt;/code&gt; : called while exiting the context, cleans up resources. It is called on the original class</li>
</ol>