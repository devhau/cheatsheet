# container

```php
App::bind('foo', function($app){ return new Foo; });
App::make('foo');
// If this class exists, it's returned
App::make('FooBar');
// Register a shared binding in the container
App::singleton('foo', function(){ return new Foo; });
// Register an existing instance as shared in the container
App::instance('foo', new Foo);
// Register a binding with the container
App::bind('FooRepositoryInterface', 'BarRepository');
// Register a service provider with the application
App::register('FooServiceProvider');
// Listen for object resolution
App::resolving(function($object){});
```