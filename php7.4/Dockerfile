FROM php:7.4-fpm-alpine

RUN apk update && apk add --no-cache autoconf g++ make git zip postgresql-dev libpng-dev libzip-dev && \
    docker-php-ext-install pdo_pgsql opcache bcmath sockets exif gd zip
RUN pecl install -o -f redis \
    &&  rm -rf /tmp/pear \
    &&  docker-php-ext-enable redis
