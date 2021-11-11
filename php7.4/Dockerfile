FROM php:7.4-fpm-alpine

RUN apk update && apk add --no-cache git zip postgresql-dev libpng-dev libzip-dev && \
    docker-php-ext-install pdo_pgsql opcache bcmath sockets exif gd zip
RUN mkdir -p /usr/src/php/ext/redis \
    && curl -L https://github.com/phpredis/phpredis/archive/5.3.4.tar.gz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
    && echo 'redis' >> /usr/src/php-available-exts \
    && docker-php-ext-install redis
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
