FROM php:5.6-fpm-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

RUN apk update && apk add --no-cache autoconf openssl-dev g++ make libmcrypt \
    libmcrypt-dev libpng-dev libxml2 libxml2-dev \
    && pecl install mongo \
    && docker-php-ext-install pdo_mysql mcrypt mbstring gd zip xml \
    && docker-php-ext-enable mongo \
    && apk del --purge autoconf openssl-dev g++ make

USER www-data
