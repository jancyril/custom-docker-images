FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libmcrypt-dev \
        libpng-dev \
        libxml2-dev \
        libonig-dev \
        libimage-exiftool-perl \
    && pecl install mcrypt-1.0.3 \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd pdo_mysql mbstring exif \
    && docker-php-ext-enable mcrypt \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/bin/composer

USER www-data

WORKDIR /var/www/html
