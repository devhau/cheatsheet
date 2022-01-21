# Helper

## Arrays
```php
// adds a given key / value pair to the array if the
// given key doesn't already exist in the array
array_add($array, 'key', 'value');
// collapse an array of arrays into a single array
array_collapse($array);
// Divide an array into two arrays. One with keys and the other with values
array_divide($array);
// Flatten a multi-dimensional associative array with dots
array_dot($array);
// Get all of the given array except for a specified array of items
array_except($array, array('key'));
// Return the first element in an array passing a given truth test
array_first($array, function($key, $value){}, $default);
// Strips keys from the array
array_flatten($array);
// Remove one or many array items from a given array using "dot" notation
array_forget($array, 'foo');
// Dot notation
array_forget($array, 'foo.bar');
// Get an item from an array using "dot" notation
array_get($array, 'foo', 'default');
array_get($array, 'foo.bar', 'default');
// Checks that a given item exists in an array using "dot" notation
array_has($array, 'products.desk');
// Get a subset of the items from the given array
array_only($array, array('key'));
// Return array of key => values
array_pluck($array, 'key');
// Return and remove 'key' from array
array_pull($array, 'key');
// Set an array item to a given value using "dot" notation
array_set($array, 'key', 'value');
// Dot notation
array_set($array, 'key.subkey', 'value');
// Sorts the array by the results of the given Closure
array_sort($array, function(){});
// Recursively sorts the array using the sort function
array_sort_recursive();
// Filters the array using the given Closure
array_where();
// First element of an array
head($array);
// Last element of an array
last($array);
```

## Paths
```php
// Fully qualified path to the app directory
app_path();
// Get the path to the public folder
base_path();
// Fully qualified path to the application configuration directory
config_path();
// Fully qualified path to the application's database directory
database_path();
// Gets the path to the versioned Elixir file:
elixir();
// Fully qualified path to the public directory
public_path();
// Get the path to the storage folder
storage_path();
```
## Strings
```php             

// Convert a value to camel case
camel_case($value);
// Get the class "basename" of the given object / class
class_basename($class);
// Escape a string
e('<html>');
// Determine if a given string starts with a given substring
starts_with('Foo bar.', 'Foo');
// Determine if a given string ends with a given substring
ends_with('Foo bar.', 'bar.');
// Convert a string to snake case
snake_case('fooBar');
// Limits the number of characters in a string
str_limit();
// Determine if a given string contains a given substring
str_contains('Hello foo bar.', 'foo');
// Result: foo/bar/
str_finish('foo/bar', '/');
str_is('foo*', 'foobar');
str_plural('car');
str_random(25);
str_singular('cars');
str_slug("Laravel 5 Framework", "-");
// Result: FooBar
studly_case('foo_bar');
trans('foo.bar');
trans_choice('foo.bar', $count);
```
## URLs and Links
```php              

action('FooController@method', $parameters);
// HTML Link
asset('img/photo.jpg', $title, $attributes);
// HTTPS link
secure_asset('img/photo.jpg', $title, $attributes);
route($route, $parameters, $absolute = true);
url('path', $parameters = array(), $secure = null);
              
Miscellaneous
// Authenticator instance (Auth)
auth()->user();
// Generates a redirect response to the user's previous location
back();
// Hashes the given value using Bcrypt (Hash)
bcrypt('my-secret-password');
// Creates a collection instance from the supplied items
collect(['taylor', 'abigail']);
// Gets the value of a configuration variable
config('app.timezone', $default);
// Generates an HTML hidden input field containing the value of the CSRF token
{!! csrf_field() !!}
// Retrieves the value of the current CSRF token
$token = csrf_token();
// Dumps the given variable and ends execution of the script
dd($value);
// Gets the value of an environment variable or returns a default value
$env = env('APP_ENV');
$env = env('APP_ENV', 'production');
// Dispatches the given event to its listeners:
event(new UserRegistered($user));
// Creates a model factory builder for a given class
$user = factory(App\User::class)->make();
// Generates an HTML hidden input field containing the spoofed value of the form's HTTP verb
{!! method_field('delete') !!}
// Retrieves an old input value flashed into the session
$value = old('value');
$value = old('value', 'default');
// Returns an instance of the redirector to do redirects:
return redirect('/home');
// Returns the current request instance or obtains an input item
$value = request('key', $default = null)
// Creates a response instance or obtains an instance of the response factory
return response('Hello World', 200, $headers);
// Used to get / set a session value
$value = session('key');
$value = session()->get('key');
session()->put('key', $value);
// Will simply return the value it is given.
value(function(){ return 'bar'; });
// Retrieves a view instance
return view('auth.login');
// Returns the value it is given
$value = with(new Foo)->work();
```