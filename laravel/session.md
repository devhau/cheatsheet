# Session 

```php
Session::get('key');
// Returns an item from the session
Session::get('key', 'default');
Session::get('key', function(){ return 'default'; });
// Get the session ID
Session::getId();
// Put a key / value pair in the session
Session::put('key', 'value');
// Push a value into an array in the session
Session::push('foo.bar','value');
// Returns all items from the session
Session::all();
// Checks if an item is defined
Session::has('key');
// Remove an item from the session
Session::forget('key');
// Remove all of the items from the session
Session::flush();
// Generate a new session identifier
Session::regenerate();
// Flash a key / value pair to the session
Session::flash('key', 'value');
// Reflash all of the session flash data
Session::reflash();
// Reflash a subset of the current flash data
Session::keep(array('key1', 'key2'));
```