FROM php:7-fpm-alpine

LABEL maintainer="JC Segubience <jc@segubience.com>"

RUN apk update && apk add --no-cache gcc make autoconf libc-dev \
    libmcrypt-dev libpng-dev libxml2-dev libzip-dev \
    && pecl install mcrypt-1.0.2 \
    && docker-php-ext-enable mcrypt \
    && docker-php-ext-install pdo_mysql mbstring zip \
    && docker-php-ext-install gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer

USER www-data

WORKDIR /app
