# Route

```php
Route::get('foo', function(){});
Route::get('foo', 'ControllerName@function');
Route::controller('foo', 'FooController');
              
RESTful Controllers 
Route::resource('posts','PostsController');
//Specify a subset of actions to handle on the route
Route::resource('photo', 'PhotoController',['only' => ['index', 'show']]);
Route::resource('photo', 'PhotoController',['except' => ['update', 'destroy']]);
              
Triggering Errors 
App::abort(404);
$handler->missing(...) in ErrorServiceProvider::boot();
throw new NotFoundHttpException;
              
Route Parameters 
Route::get('foo/{bar}', function($bar){});
Route::get('foo/{bar?}', function($bar = 'bar'){});
              
HTTP Verbs
Route::any('foo', function(){});
Route::post('foo', function(){});
Route::put('foo', function(){});
Route::patch('foo', function(){});
Route::delete('foo', function(){});
// RESTful actions
Route::resource('foo', 'FooController');
// Registering A Route For Multiple Verbs
Route::match(['get', 'post'], '/', function(){});
              
Secure Routes(TBD)
Route::get('foo', array('https', function(){}));
              
Route Constraints
Route::get('foo/{bar}', function($bar){})
->where('bar', '[0-9]+');
Route::get('foo/{bar}/{baz}', function($bar, $baz){})
->where(array('bar' => '[0-9]+', 'baz' => '[A-Za-z]'))
              
// Set a pattern to be used across routes
Route::pattern('bar', '[0-9]+')
              
HTTP Middleware 
// Assigning Middleware To Routes
Route::get('admin/profile', ['middleware' => 'auth', function(){}]);
              
Named Routes
Route::currentRouteName();
Route::get('foo/bar', array('as' => 'foobar', function(){}));
Route::get('user/profile', [
  'as' => 'profile', 'uses' => 'UserController@showProfile'
]);
$url = route('profile');
$redirect = redirect()->route('profile');
              
Route Prefixing
Route::group(['prefix' => 'admin'], function()
{
  Route::get('users', function(){
      return 'Matches The "/admin/users" URL';
  });
});
              
Route Namespacing
// This route group will carry the namespace 'Foo\Bar'
Route::group(array('namespace' => 'Foo\Bar'), function(){})
              
Sub-Domain Routing
// {sub} will be passed to the closure
Route::group(array('domain' => '{sub}.example.com'), function(){});
``