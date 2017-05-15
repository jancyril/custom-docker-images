FROM php:7.1-alpine

LABEL maintainer Jan Cyril Segubience <jancyril@segubience.com>

ENV QUEUE_CONNECTION=redis
ENV TRIES=3
ENV PROCESSES=1

ADD supervisord.conf /etc/supervisor/supervisord.conf

RUN apk update && apk add --no-cache python py-pip && \
    pip install supervisor

VOLUME /app

ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisor/supervisord.conf"]
