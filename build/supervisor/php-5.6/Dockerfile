FROM jancyril/php:5.6-fpm-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

USER root

RUN apk add --no-cache python py-pip && pip install supervisor

USER www-data

ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/supervisord.conf"]
