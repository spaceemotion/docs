---
layout: default
title: Memory Component

---

Memory Component
==============

* [Installation](#installation)
* [Configuration](#configuration)

<article id="introduction">

`Orchestra\Memory` handles runtime configuration either using "in memory" Runtime or database using Cache, Fluent Query Builder or Eloquent ORM. Instead of just allowing static configuration to be used, `Orchestra\Memory` allow those configuration to be persistent in between request by utilizing multiple data storage option either through cache or database.

</article>

<article id="installation">
## Installation

To install through composer, simply put the following in your `composer.json` file:

	{
		"require": {
			"orchestra/memory": "2.0.*"
		},
		"minimum-stability": "dev"
	}

</article>

<article id="configuration">
## Configuration

Next add the service provider in `app/config/app.php`.

	'providers' => array(
		
		// ...
		
		'Orchestra\Memory\MemoryServiceProvider',
	),

<a id="migrate"></a>
### Migrations

Before we can start using `Orchestra\Memory`, please run the following:

	$ php artisan orchestra:memory install

<a id="config-publish"></a>
### Publish Configuration

Optionally, you can also publish the configuration file if there any requirement to change the default:

	$ php artisan config:publish --packages=orchestra/memory

</article>