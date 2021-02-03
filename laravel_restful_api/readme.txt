ref: https://medium.com/@newaeonweb/laravel-restful-api-using-docker-in-three-steps-63a5b4c8f211

# Steps after : docker-compose up -d
1. docker-compose exec php-fpm bash
2. composer create-project laravel/laravel=5.6.12 server — prefer-dist
3. Open docker-compose.yml and let’s adjust the php-fpm volumes tag with the new path
3.1 volumes:
- ./server:/application
- ./phpdocker/php-fpm/php-ini-overrides.ini:/etc/php/7.2/fpm/conf.d/99-overrides.ini
stop and restart our containers
4. exit to exit the php-fpm bash
5. docker-compose kill
6. docker-compose up -d

# Configuring the .env file.
1. Open .env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=databasename
DB_USERNAME=databaseuser
DB_PASSWORD=123456
2. docker-compose exec php-fpm bash
2.1 php artisan tinker
2.2 DB::connection()->getDatabaseName();

# Creating Migrations and Database seed.
1. docker-compose exec php-fpm bash
2. php artisan make:model Band -m
3. Open server/app/Band.php
3.1 
protected $fillable = [
   'name',
   'country',
   'genre'
]; 
3.2 Open server/database/migrations/####_##_##_######_create_bands_table.php
$table->string('name');
$table->string('country');
$table->string('genre');
4. php artisan migrate





