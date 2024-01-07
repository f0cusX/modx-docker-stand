# Info

Modx docker stand.

## Configuration
* Modx 2.8.6-pl
* Nginx
* Mysql 5.7 + PhpMyAdmin
* PHP-fpm 7.3

## Start
* Copy `.env.dist` to `.env` and set root mysql password.
* Run `docker-compose -f docker-compose.yml up -d --build`.
* Open `http://localhost/setup`
* Set database server `mysql` instead `localhost`. User, database and password = `modx`