FROM php:7-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

RUN apk update && apk add --no-cache libmcrypt libmcrypt-dev libpng-dev libxml2-dev \
    && docker-php-ext-install pdo_mysql mcrypt mbstring gd zip \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer

USER www-data

WORKDIR /app
