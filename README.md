# Description
Based on https://github.com/Sylius/Docker

This Docker Compose development environment includes

* PHP 7.0
* MariaDB
* Composer
* NodeJS (v6)

# Usage
First, clone Sylius repository https://github.com/Sylius/Sylius

You need to install Docker and Docker Compose.

```bash
mkdir docker
cd docker
docker-compose up
```

# Run

NodeJS container start, run: npm install && npm run gulp
and down.

PHP container run: bin/console server:start 0.0.0.0:8000 command

If your database is not installed, enter in PHP container:

```bash
docker-compose exec php bash
```

And run Sylius install command from PHP container:
```bash
php bin/console sylius:install
```

Now you access to front and back-office.

### Website
##### Admin
http://localhost:8000/admin

##### Front office
http://localhost:8000

## Tips
Execute commands in nodeJS container, like install npm packages.
```bash
docker run --rm -it -v $(pwd):/var/www/sylius -w /var/www/sylius node:6 sh
````

Run Gulp watch for sass CSS
```bash
docker-compose run --rm node ./node_modules/.bin/gulp shop-watch
````
