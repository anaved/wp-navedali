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
Context managers are inherent feature of python to provide a way to obtain and release resources on demand. When a context manager is used, a definite scope is defined to safely delete or clean resources. <span/>For example a file can be read in below two ways.
https://gist.github.com/anaved/437ed10fa2c2a4f3252e715aa2f2b006#file-file_read_in_context-py
<ol>
	<li>In this method, python interpreter has no way to estimate the need for myFile in future. Hence it holds on to the file descriptor until the program scope.</li>
	<li>This method of file access ensures a clear scope of the usage of the resource file test.txt. This file is closed at the end of the block, and any file descriptor associated is released. This cleanup is performed behind the scenes as an effect of opening he file in a context.</li>
</ol>
<h5>To achieve such behavior a class must define below two methods.</h5>
<ol>
	<li>
		<code>__enter__</code>: called at the time of entering the context, allocates resources
		<ul>
			<li>Return value shall be the handle to the object we want to pass for further operation within the block.</li>
			<li>
				<span/>Most common is to to return self here.</li>
			<li>If an Exception is raise on the <code>__init__</code> or the <code>__enter__</code> method, then setup is considered invalid and <code>__exit__</code> is not called</li>
		</ul>
	</li>
	<li>
		<code>__exit__</code>: called while exiting the context, cleans up resources.
		<ul>
			<li>It is called on the original class</li>
			<li>Can suppress errors by returning True</li>
		</ul>
	</li>
</ol>
<h5>Examples of usage of context managers.</h5>
<ol>
	<li> Create multiple patches inside a singular context
	</li>
https://gist.github.com/anaved/437ed10fa2c2a4f3252e715aa2f2b006#file-context_manager-py
	<li> Exception flow
	</li>
https://gist.github.com/anaved/437ed10fa2c2a4f3252e715aa2f2b006#file-exception_in_context-py

</ol>