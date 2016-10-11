Setup Project Laravel project in c9.io

- Create an account c9.io
- Create a workspace
- Setup database
- Setup phpmyadmin
- Start your laravel


https://laracasts.com/discuss/channels/tips/testing-cloud9-ide-with-composer-laravel

Install Laravel 5.3

rm README.md php.ini hello-world.php
sudo composer self-update
composer create-project laravel/laravel ./laravel --prefer-dist 5.3
shopt -s dotglob
mv laravel/* ./
rm -rf laravel

Update the conf file

sudo nano /etc/apache2/sites-enabled/001-cloud9.conf

at the end of line 2
DocumentRoot /home/ubuntu/workspace/public

Press F2 or Ctrl/Cmd + X to exit, then y and return to save.

Get the latest version of Laravel

sudo composer update

Set up your database

mysql-ctl cli
use c9;
select @@hostname;
exit

Add the database details to your .env file.

DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=c9
DB_USERNAME=USERNAME (this must be your cloud9 username, not just 'USERNAME')
DB_PASSWORD=

Using phpmyadmin

phpmyadmin-ctl install

Update NPM and node

sudo npm install -g n
sudo n latest
sudo npm install -g npm
npm install

Start your laravel or click run

php artisan serve
