# Event 
```php
Event::fire('foo.bar', array($bar));
// Register an event listener with the dispatcher.
// void listen(string|array $events, mixed $listener, int $priority)
Event::listen('App\Events\UserSignup', function($bar){});
Event::listen('foo.*', function($bar){});
Event::listen('foo.bar', 'FooHandler', 10);
Event::listen('foo.bar', 'BarHandler', 5);
// Stopping The Propagation Of An Event
// You may do so using by returning false from your handler.
Event::listen('foor.bar', function($event){ return false; });
Event::subscribe('UserEventHandler');
```