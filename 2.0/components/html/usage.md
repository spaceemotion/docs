---
layout: docs2.0
title: Using HTML

---

Using HTML
==============

<article id="introduction">

`Orchestra\Html\HtmlBuilder` is a small improvement from `Illuminate\Html\HtmlBuilder`.

> Advise to use this only when manipulating HTML outside of view, otherwise it's better (and faster) to use html.

</article>

<article id="create">
## Create HTML

Create a HTML tag from within your libraries/extension using following code:

	echo HTML::create('p', 'Some awesome information');
	
	// will output <p>Some awesome information</p>

You can customize the HTML attibutes by adding third parameter.

	echo HTML::create('p', 'Another awesomeness', ['id' => 'foo']);
	
	// will output <p id="foo">Another awesomeness</p>
	
</article>

<article id="raw">
## Raw HTML Entities

Mark a string to be excluded from being escaped.

	echo HTML::link('foo', HTML::raw('<img src="foo.jpg">'));
	
	// will output <a href="foo"><img src="foo.jpg"></a>
</article>

<article id="decorate">
## Decorate HTML

Decorate method allow developer to define HTML attributes collection as `HTML::attributes` method, with the addition of including default attributes array as second parameter.

	return HTML::decorate(
    	['class' => 'foo'], 
    	['id' => 'foo', 'class' => 'span5']
	);
	
	// will return array('class' => 'foo span5', 'id' => 'foo');

It also support replacement of default attributes if such requirement is needed.

	$attributes = HTML::decorate(
	    ['class' => 'foo !span5'],
	    ['class' => 'bar span5'],
	);

	// will return array('class' => 'foo bar');

</article>