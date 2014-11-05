TinyLara\TinyRoute
=====
[![Latest Stable Version](https://poser.pugx.org/tinylara/tinyroute/v/stable.svg)](https://packagist.org/packages/tinylara/tinyroute) [![Total Downloads](https://poser.pugx.org/tinylara/tinyroute/downloads.svg)](https://packagist.org/packages/tinylara/tinyroute) [![Latest Unstable Version](https://poser.pugx.org/tinylara/tinyroute/v/unstable.svg)](https://packagist.org/packages/tinylara/tinyroute) [![License](https://poser.pugx.org/tinylara/tinyroute/license.svg)](https://packagist.org/packages/tinylara/tinyroute)

TinyRoute is a tiny PHP router based on [Macaw](https://github.com/NoahBuscher/Macaw).

### Install

If you have Composer, just include TinyRoute as a project dependency in your `composer.json`. If you don't just install it by downloading the .ZIP file and extracting it to your project directory.

```
require: {
    "tinylara/tinyroute": "dev-master"
}
```

### Examples

```php
use TinyLara\TinyRoute\TinyRoute as Route;

Route::get('', 'HomeController@home');

Route::get('foo', function() {
  echo "Foo!";
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

The TinyRoute is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
