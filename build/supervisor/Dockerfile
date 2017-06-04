FROM php:7.1-alpine

LABEL maintainer="Jan Cyril Segubience <jancyril@segubience.com>"

RUN apk update && apk add --no-cache python py-pip \
    && pip install supervisor

ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/supervisord.conf"]
