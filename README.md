This project includes:
* PHP 7
* Nginx
* MariaDb
* Symfony 4

Make sure you have installed docker & docker-compose

In the same folder with docker-compose.yml run:
 
```
docker-compose build
docker-compose up -d
```

If command log didn't have errors and all containers are up and running 
(to check run "docker ps"), you may open browser with "localhost" 
domain and check output.

There will be errors in output. Still don't have dependencies. 
To add them enter to the container and install them:

```
docker-compose exec php-fpm composer install
```

After command finished - check browsed again. 
Hello world must be there ;)

 
