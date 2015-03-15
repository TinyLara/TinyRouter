TinyLara\TinyRouter
=====
[![Latest Stable Version](https://poser.pugx.org/tinylara/tinyrouter/v/stable.svg)](https://packagist.org/packages/tinylara/tinyrouter) [![Total Downloads](https://poser.pugx.org/tinylara/tinyrouter/downloads.svg)](https://packagist.org/packages/tinylara/tinyrouter) [![License](https://poser.pugx.org/tinylara/tinyrouter/license.svg)](https://packagist.org/packages/tinylara/tinyrouter)

TinyRouter is a tiny PHP router based on [Macaw](https://github.com/NoahBuscher/Macaw). [Read the documentation.](https://github.com/TinyLara/TinyLara/wiki/Routing)

### Install

If you have Composer, just include TinyRouter as a project dependency in your `composer.json`. If you don't just install it by downloading the .ZIP file and extracting it to your project directory.

```
require: {
    "tinylara/tinyrouter": "*"
}
```

### Examples

```php
use TinyLara\TinyRouter\TinyRouter as Route;

Route::get('/', 'HomeController@home');

// GET
Route::get('foo', function() {
  echo "GET Foo!";
});
// POST
Route::post('foo', function() {
  echo "POST Foo!";
});
// ANY: GET or POST
Route::any('foo', function() {
  echo "ANY Foo!";
});

Route::error(function() {
  throw new Exception("404 Not Found");
});

Route::dispatch();
```

The `Route::dispatch()` function can receive a parameter as the Processor After. It will process the value returned by Controller. Example:

```php
Route::dispatch('View@process');
```
<br>
If you don't specify an error callback, it will just echo `404`.

### License

The TinyRouter is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
