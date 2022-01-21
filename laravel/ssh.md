# SSH

```
Executing Commands
SSH::run(array $commands);
SSH::into($remote)->run(array $commands); 
// specify remote, otherwise assumes default
SSH::run(array $commands, function($line)
{
  echo $line.PHP_EOL;
});
              
Tasks
// define
SSH::define($taskName, array $commands);
// execute
SSH::task($taskName, function($line)
{
  echo $line.PHP_EOL;
});
              
SFTP Uploads
SSH::put($localFile, $remotePath);
SSH::putString($string, $remotePath);
```