# laravel-orbit-HTMLDriver
A HTML driver for laravel orbit, a flat-file driver for Laravel Eloquent. Supports Jekyll Markdown, HTML + YAML front matter.

## Installation

Install via composer by running this in your terminal:

```sh
composer require ryangjchandler/orbit
```

## Usage

Go into your orbit config file `config/orbit.php`. If you cant find it, publish it by running this in your terminal:

```sh
php artisan vendor:publish --provider="Orbit\\OrbitServiceProvider"
```

In the config file, add the HTML Driver and configure it as default driver:

```php
<?php

return [

    'default' => env('ORBIT_DEFAULT_DRIVER', 'html'), # <-- Change here to html

    'drivers' => [
        'html' => \Alexanderhorner\LaravelOrbitHtmlDriver\Driver\HTMLDriver::class, # <-- Add this line to your drivers array here

        'md' => \Orbit\Drivers\Markdown::class,
        'json' => \Orbit\Drivers\Json::class,
        'yaml' => \Orbit\Drivers\Yaml::class,
        'md_json' => \Orbit\Drivers\MarkdownJson::class,
    ],
    
...
```

This should be it. New database entries should now create html files with yaml front matter.
