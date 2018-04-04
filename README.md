Make sure you have installed docker & docker-compose (v.2)

Make symbolic link for code (project may be placed anywhere, it's just an example):

```
ln -s ./project/ ./code
```

In the folder with docker-compose.yml run:
 
```
docker-compose build
docker-compose up -d
```

If command log didn't have errors and all containers is up 
(to check run "docker ps"), you may open browser with "localhost" 
domain and check output.

There may be errors in output. Still don't have dependencies. 
To add them enter to the container and install them:

```
docker-compose exec php-fpm composer install
```

After command finished - check browsed again. 
Hello world must be there ;)

 
