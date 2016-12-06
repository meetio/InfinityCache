# InfinityCache
A fork of Morilog's InfinityCache-package. A Laravel package for Eloquent cache. InfinityCache provides infinity and forever cache for queries results until the model changes. If a model has been created, deleted or updated, model queries caches will be flushed.

### Requirements
This package works only with ***taggable cache storages*** and drivers such as `memcached` or `Redis` and other storages that extended from `Illuminate\Cache\TaggedCache`.

### Installation
To install this package run this composer command:
~~~ bash
composer require morilog/infinity-cache
~~~

Add the ServiceProvider to your `config/app.php` providers array:
~~~ php
    'providers' => [
        ...
        Meetio\InfinityCache\InfinityCacheServiceProvider::class,
        ...
    ]
~~~

Then publish the config file:
~~~ php
php artisan vendor:publish --provider="Meetio\InfinityCache\InfinityCacheServiceProvider" --tag="config"
~~~

### Usage
For using InfinityCache, your eloquent model must extend `Meetio\InfinityCache\Model` 

example:
~~~ php
<?php
namespace App\Models;

use Meetio\InfinityCache\Model as InfinityCacheModel;

class Post extends InfinityCacheModel
{
  ...
}
~~~
