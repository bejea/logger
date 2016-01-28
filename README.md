# logger
A terrible logger utility for PHP (syntax same as [noodlehaus/logger](https://github.com/noodlehaus/logger))

## Example

```php
<?php
require __DIR__.'/logger.php';

# logger is active based on truthiness of an expression
$debug = logger('./debug.log', getenv('PHP_ENV') === 'TEST');
$debug('This will show up if PHP_ENV is set to TEST');

# logger is active based result of callable
$info = logger('./info.log', function () {
  return true;
});
$info('This should show up');

# works like printf
$name = 'noodlehaus';
$info('Hello there %s', $name);

# defaults
$always = logger('./file.log');
$always('This always gets logged.');
```
