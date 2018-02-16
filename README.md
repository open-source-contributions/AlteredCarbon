AlteredCarbon
=============

This Library extends the Carbon\Carbon class to include extra support for other DateTime formats and in particular the NotSO8601 datetime format.


## Functions
### __constructor()
```php
<?php
$stringNotSO8601 = '20180215135543:Australia/Brisbane';

$alteredCarbon = new Mossengine\AlteredCarbon\AlteredCarbon($stringNotSO8601);

$alteredCarbon->toDateTimeString();
// -> 2018-02-15 13:55:43

$alteredCarbon->getTimezone()->getName();
// -> Australia/Brisbane
```

### createFromNotSO8601()
```php
<?php
$stringNotSO8601 = '20180215135543:Australia/Brisbane';

$alteredCarbon = Mossengine\AlteredCarbon\AlteredCarbon::createFromNotSO8601($stringNotSO8601);

$alteredCarbon->toDateTimeString();
// -> 2018-02-15 13:55:43

$alteredCarbon->getTimezone()->getName();
// -> Australia/Brisbane
```

### toNotSO8601String()
```php
<?php
$stringDateTime = '2018-02-15 13:55:43';
$stringTimeZone = 'Australia/Brisbane';

$alteredCarbon = new Mossengine\AlteredCarbon\AlteredCarbon($stringDateTime, $stringTimeZone);

$alteredCarbon->toNotSO8601String();
// -> 20180215135543:Australia/Brisbane 
```

## Installation

### With Composer

```
$ composer require mossengine/alteredcarbon
```

```json
{
    "require": {
        "mossengine/alteredcarbon": "~1.0.0"
    }
}
```

```php
<?php
require 'vendor/autoload.php';

use Mossengine\AlteredCarbon\AlteredCarbon;

printf("NotSO8601 Now: %s", AlteredCarbon::now()->toNotSO8601String());
```


### Without Composer

Why are you not using [composer](http://getcomposer.org/)? Download [Carbon.php](https://github.com/briannesbitt/Carbon/blob/master/src/Carbon/Carbon.php) from the repo and save the file into your project path somewhere.

```php
<?php
require 'path/to/AlteredCarbon.php';

use Mossengine\AlteredCarbon\AlteredCarbon;

printf("NotSO8601 Now: %s", AlteredCarbon::now()->toNotSO8601String());
```