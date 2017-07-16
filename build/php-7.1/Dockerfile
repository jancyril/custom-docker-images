FROM php:7.1-fpm-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

RUN apk update && apk add --no-cache libmcrypt libmcrypt-dev libpng-dev libxml2-dev \
    && docker-php-ext-install pdo_mysql mcrypt mbstring gd zip
