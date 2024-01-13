# Laravel Documents
Deploy Laravel Project from Localhost to Shared Hosting without SSH


1-edit .env file as below :

DB_CONNECTION=mysql
APP_NAME=appname
APP_ENV=production
APP_KEY=base64key
APP_DEBUG=false
APP_URL=https://domain.com
DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=dbname
DB_USERNAME=dbuser
DB_PASSWORD=dbuserpass


2-Run these artisan commands in cmd and project folder
php artisan key:generate
php artisan config:cache
php artisan config:clear
php artisan route:cache
php artisan serve

3-Now make a zip file of your local host folder and .sql of your db
4-Upload them in your shared hosting cpanel or directadmin
5-Check your php version to be the same as your local project is.
6-Move index from public folder to main folder
7-Now we need to modify two lines  of the index.php. Open index.php and change like this:
Remove /.. in these lines :
-----
require __DIR__.'/../vendor/autoload.php';
-----
$app = require_once __DIR__.'/../bootstrap/app.php';

8-Finally move .htaccess from public folder to main folder
9-And change domain to new domain in that if necessary.

10-Remove “/public” in resources/views/
![image](https://github.com/alirezadamash/laravel-document/assets/10388752/8a0e325e-7954-49bc-8b9c-12056691f4fb)
