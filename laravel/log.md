# Log

```php
// The logger provides the seven logging levels defined in RFC 5424:
// debug, info, notice, warning, error, critical, and alert.
Log::info('info');
Log::info('info',array('context'=>'additional info'));
Log::error('error');
Log::warning('warning');
// get monolog instance
Log::getMonolog();
// add listener
Log::listen(function($level, $message, $context) {});
              
Query Logging 
// enable the log
DB::connection()->enableQueryLog();
// get an array of the executed queries
DB::getQueryLog();
```