# Lista de Tareas de Laravel

DROP DATABASE `bd_mrp`;
CREATE DATABASE `bd_mrp` /*!40100 COLLATE 'utf8_general_ci' */;
SHOW DATABASES;
USE `bd_mrp`;


Primeros Pasos al clonar un repositorio: 

composer install 
composer install --ignore-platform-reqs   //cuando sabes que quieres instalar si o si
$ cp .env.example .env
$ php artisan key:generate


$ ncu   //verificar las versiones de dependencias
ncu -u  //actualiza las dependencias 

npm install 
npm run dev 

git init
git add -A
git commit -m "comentario"
git push origin main (antes era master) 

php artisan make:model Tabla -c 
php artisan tinker 
php artisan make:model Post -mc   //crea el modelo, migracion y controlador
$products = App\Product::all();

git reset --hard HEAD^     moverse entre los commits


git pull  (actualizar el repositorio local)
git pull uspstream  (actualizar repositorio para los que hacen fork) + main (rama del upstream)

php artisan make:migration create_posts_table   
php artisan migrate:status
php artisan migrate:refresh 	no emplear con datos  
php artisan route:list 		ver todas las rutas


php artisan migrate:refresh --seed    ejecuta los seedersg

Ctrl+Shift+L  para resaltar las palabras que coinciden

$user = User::with("posts")->find(1);

Si deseas eliminar un paquete de Laravel usando PHP composer:
composer remove vendor/package	ejemp composer remove barryvdh/laravel-debubar

