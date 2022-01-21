# Environment

```php
$environment = app()->environment();
$environment = App::environment();
$environment = $app->environment();
// The environment is local
if ($app->environment('local')){}
// The environment is either local OR staging...
if ($app->environment('local', 'staging')){}
```