FROM jancyril/php:5.6-fpm-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer

USER www-data

WORKDIR /app
