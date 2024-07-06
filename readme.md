# Nginx as reverse proxy for Laravel Docker container

## List of commands followed for Dockerfiles

#### Containers

```
docker build -t borathiago/nginx:production . -f Dockerfile.production
```

```
docker build -t borathiago/laravel:production laravel -f laravel/Dockerfile.production
```

#### Networks and linked ports

```
docker run -d --network laravelnginx --name laravel borathiago/laravel:production
```

```
docker run -d --network laravelnginx --name nginx -p 8080:80 borathiago/nginx:production
```

## Otherwise docker-compose could be used

```
docker compose up -d
```

#### Rebuild images
````
docker compose up -d --build
```



