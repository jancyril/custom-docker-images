FROM php:5.6-fpm-alpine

LABEL maintainer "Jan Cyril Segubience <jancyril@segubience.com>"

RUN apk update && apk add --no-cache autoconf openssl-dev g++ make libmcrypt \
    && libmcrypt-dev libpng-dev libxml2 libxml2-dev \
    && pecl install mongo \
    && docker-php-ext-install pdo_mysql mcrypt mbstring gd zip xml \
    && docker-php-ext-enable mongo \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer \
    && apk del --purge autoconf openssl-dev g++ make

USER www-data
