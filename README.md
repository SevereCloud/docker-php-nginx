# Docker Compose nginx + php

Репозиторий для быстрого развертывания nginx + php в докере(**без mysql**)

`hosts` - конфигурация nginx

`images/php` - образ php с нужными расширениями

`logs` - логи nginx

`www` - файлы сайта

## Запуск

```sh
# git clone git@github.com:SevereCloud/docker-php-nginx.git folder && cd folder
docker-compose up -d --force-recreate --build
```

Внешний nginx

```nginx
server {
  listen 80;
  server_name exaple.com;
  location / {
    proxy_pass http://ip-docker:80;
  }
}
```