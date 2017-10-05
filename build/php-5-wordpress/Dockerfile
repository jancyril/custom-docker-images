FROM php:5.6-fpm-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

RUN apk update && apk add --no-cache autoconf openssl-dev g++ make libmcrypt \
    libmcrypt-dev libpng-dev libxml2 libxml2-dev libxslt libxslt-dev \
    && docker-php-ext-install gd mcrypt mbstring pdo_mysql mysql xml xsl zip \
    && apk del --purge autoconf openssl-dev g++ make
