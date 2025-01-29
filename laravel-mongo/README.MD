# Uso de MongoDB con Laravel

Este documento describe cómo configurar y utilizar MongoDB en una aplicación Laravel.

## Instalación
Para habilitar el uso de MongoDB en Laravel, se debe instalar la librería correspondiente mediante Composer:

```sh
composer require mongodb/laravel-mongodb
```

## Configuración
### 1. Registrar el proveedor de servicios
Después de la instalación, es necesario registrar el proveedor en el archivo `config/app.php` dentro de la sección `providers`:

```php
'MongoDB\Laravel\MongoDBServiceProvider::class',
```

### 2. Configurar la conexión en `config/database.php`
Se debe agregar la configuración de conexión para MongoDB dentro del array `connections` en `config/database.php`:

```php
'connections' => [
    'mongodb' => [
        'driver'   => 'mongodb',
        'host'     => env('DB_HOST', '127.0.0.1'),
        'port'     => env('DB_PORT', 27017),
        'database' => env('DB_DATABASE', 'homestead'),
        'username' => env('DB_USERNAME', 'homestead'),
        'password' => env('DB_PASSWORD', 'secret'),
        'options'  => [
            'appname' => 'homestead',
        ],
    ],

    'sqlite' => [
        'driver'   => 'sqlite',
        'url'      => env('DATABASE_URL'),
    ],
],
```

## Conclusión
Después de realizar estas configuraciones, Laravel podrá interactuar con MongoDB como su base de datos principal o secundaria, permitiendo aprovechar sus ventajas en proyectos escalables.

