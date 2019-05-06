# Laravel Simple Message Trait

Laravel provides a `SimpleMessage` class for mail representation of notifications (https://github.com/laravel/framework/blob/5.8/src/Illuminate/Notifications/Messages/SimpleMessage.php) but sometimes you want to use this nice interface on a regular `Mailable` instance. This package is simply a copy and paste of the `SimpleMessage` class but as a trait instead of a class.

## Install

    composer require antriver/laravel-simple-message-trait

## Example

```php
<?php

namespace MySite\Mail;

use Antriver\LaravelSimpleMessageTrait\SimpleMessageTrait;
use Illuminate\Mail\Mailable;

abstract class MyCoolMailable extends Mailable
{
    use SimpleMessageTrait;

    // ...
}
```

## Notes

The `with($line)` method has been removed from the trait because that conflicts with the `with($key, $value = null)` method on `Mailable`. Instead you can use `line($line)` which does the same thing. 
