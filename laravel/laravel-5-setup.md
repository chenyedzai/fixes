# Laravel 5 Setup

1. Install [Composer](https://getcomposer.org/)

2. Require the Installer

    ```
    composer global require "laravel/installer=~1.1"
    ```

3. Add `~/.composer/vendor/bin` to your `PATH`

    ```
    export PATH="$HOME/.composer/vendor/bin:$PATH";
    ```

4. Create A New Project

    ```
    laravel new <name of site>
    ```

5. Serve the Project

    * With Artisan

      ```
      php artisan serve
      ```

    * With PHP

      ```
      php -S localhost:8000 -t public /
      ```

6. Update Composer

    ```
    composer update
    ```

_Optional: Change namespae_

```
                                                             php artisan app:name <myname>
```

### Tinkering with the commandline

 ```
php artisan tinker --env=local
```

It uses [PsySH](http://psysh.org/) a great interactive php console and debugger                         

### Installing the Debugbar

```
                                          composer require barryvdh/laravel-debugbar
```

Then add to `providers` and                    `aliases` in `config/app.php`:

```
'providers' => [
    'Barryvdh\Debugbar\ServiceProvider'
],
'aliases' => [
    'Debugbar' => 'Barry\Debugbar\Facade'
]
```

Then install the package:

```
php artisan vendor:publish
```

Logging to Debugbar:

```
                                                    \Debugbar::error('Something has gone wrong!');
```

### Testing

`PHPunit` and `PHPspec` are automatically added to `composer.json`

Check the phpunit version

```
vendor/bin/phpunit --version
```

If you can some crap error like:
```
vendor/bin/phpunit --version
You need to set up the project dependencies using the following commands:
wget http://getcomposer.org/composer.phar
php composer.phar install
```

Rather remove `vendor/`

then run `composer install`

Hopefully they fix this kak

#### Running the Test

`vendor/bin/phpunit`
