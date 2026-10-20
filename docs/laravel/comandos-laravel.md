# Comandos frecuentes de Laravel

## Base de datos (MySQL / MariaDB)

Recrear la base de datos del proyecto:

```sql
DROP DATABASE `bd_mrp`;
CREATE DATABASE `bd_mrp` /*!40100 COLLATE 'utf8_general_ci' */;
SHOW DATABASES;
USE `bd_mrp`;
```

## Primeros pasos al clonar un repositorio

```
composer install
composer install --ignore-platform-reqs   # fuerza la instalación ignorando requisitos de plataforma
cp .env.example .env
php artisan key:generate
```

## Dependencias de frontend

```
ncu         # muestra las versiones disponibles de las dependencias
ncu -u      # actualiza package.json a las últimas versiones
npm install
npm run dev
```

## Artisan

```
php artisan make:model Tabla -c               # modelo + controlador
php artisan make:model Post -mc               # modelo + migración + controlador
php artisan make:migration create_posts_table
php artisan migrate:status
php artisan migrate:refresh                   # ¡borra los datos! no usar con datos reales
php artisan migrate:refresh --seed            # recrea las tablas y ejecuta los seeders
php artisan route:list                        # lista todas las rutas
php artisan tinker
```

Ejemplos dentro de `tinker`:

```php
$products = App\Product::all();
$user = User::with("posts")->find(1);
```

## Composer

Eliminar un paquete:

```
composer remove vendor/paquete
composer remove barryvdh/laravel-debugbar     # ejemplo
```

## Atajos de VS Code

* `Ctrl+Shift+L`: selecciona todas las coincidencias de la palabra actual.

## Ver también

* [Comandos frecuentes de Git](docs/git/comandos-git.md)
