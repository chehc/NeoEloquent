# NeoEloquent

Neo4j Graph Eloquent Driver for Laravel. This is a personal-use package which is cloned from https://github.com/Vinelab/NeoEloquent.

## Quick Reference

 - [Installation](#installation)
 - [Configuration](#configuration)

## Installation

Add the package to your `composer.json` and run `composer update`.

### Laravel 5

#### 5.1

```json
{
    "require": {
        "edwinfadilah/neoeloquent": "1.2.*"
    }
}
```


Add the service provider in `app/config/app.php`:

```php
'EdwinFadilah\NeoEloquent\NeoEloquentServiceProvider',
```

The service provider will register all the required classes for this package and will also alias
the `Model` class to `NeoEloquent` so you can simply `extend NeoEloquent` in your models.

## Configuration

### Connection
in `app/config/database.php` or in case of an environment-based configuration `app/config/[env]/database.php`
make `neo4j` your default connection:

```php
'default' => 'neo4j',
```

Add the connection defaults:

```php
'connections' => [
    'neo4j' => [
        'driver' => 'neo4j',
        'host'   => 'localhost',
        'port'   => '7474',
        'username' => null,
        'password' => null,
        'ssl' => false
    ]
]
```

### Migration Setup

If you're willing to have migrations:

- create the folder `app/database/labels`
- modify `composer.json` and add `app/database/labels` to the `classmap` array
- run `composer dump-autoload`


### Documentation

For further documentation information, please see it's original repository: https://github.com/Vinelab/NeoEloquent