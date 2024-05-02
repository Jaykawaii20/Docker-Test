# Install and Set Up Laravel with Docker Compose

Setting up Laravel in the server environment with Docker using the LEMP stack that includes: Nginx, MySQL, PHP, and phpMyAdmin.

# First, Install Docker and Docker Compose
```https://docs.docker.com/engine/install/ubuntu/```

## Why use Docker for Development

- [x] Consistent development environment for the entire team.
- [x] You don't need to install a bunch of language environments on your system.
- [x] You can use different versions of the same programming language.
- [x] Deployment is easy

## How to Install and Run the Project

1. ``` git clone git@github.com:vzawft/Docker-Files-Laravel-7.git ```
2. ``` git clone git@github.com:vzawft/laravel-jetstream-inertia-vue3-nova3.git ```
3. ```sudo cp -R Docker-Files-Laravel-7/. laravel-jetstream-inertia-vue3-nova3```
3. ``` cd laravel-jetstream-inertia-vue3-nova3 ```
4. ``` sudo docker run --rm -v $(pwd):/app composer update --ignore-platform-reqs```
5. ```cp .env.example .env ``` then set the DB_HOST to db
6. ```sudo chown -R $USER:$USER ~/laravel-jetstream-inertia-vue3-nova3```
7. ```sudo docker compose up -d```
8. ```sudo docker compose exec app php artisan key:generate --ignore-platform-reqs```
9. ```sudo docker compose exec app php artisan config:cache```
8. You can see the project on ```your IP4 address ```

## If you can't clone your repo thru ssh:
```ssh-keyscan github.com >> ~/.ssh/known_hosts```

## Check your containers
```sudo docker ps```

# execute following script:
```docker-compose exec app php artisan key:generate```
and 
```docker-compose exec app php artisan config:cache```

## How to use MySQL as a database

1. Uncomment the MySQL configuration inside the ```docker-compose.yml``` including: ```db``` and ```phpMyAdmin```
2. Copy ```.env.example``` to ```.env```
3. Change ```DB_CONNECTION``` to ```mysql```
4. Change ```DB_PORT``` to ```3306```
5. Open the ```phpMyAdmin``` on ```127.0.0.1:3400```


## How to run Laravel Commands with Docker Compose

```docker-compose exec app php artisan {your command}``` 
