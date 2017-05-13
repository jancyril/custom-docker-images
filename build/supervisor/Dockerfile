FROM alpine:3.4

LABEL maintainer Jan Cyril Segubience <jancyril@segubience.com>

ADD supervisord.conf /etc/supervisor/supervisord.conf
ADD https://php.codecasts.rocks/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub

RUN echo "http://php.codecasts.rocks/7.1" >> /etc/apk/repositories && \
    apk add --update php7 && apk add --no-cache supervisor

ENTRYPOINT ["supervisord", "--nodaemon", "--configuration", "/etc/supervisord.conf"]
