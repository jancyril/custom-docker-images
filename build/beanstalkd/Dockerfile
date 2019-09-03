FROM alpine:3

LABEL maintainer="JC Segubience <jc@segubience.com>"

RUN apk update && apk add --no-cache beanstalkd

EXPOSE 11300

CMD ["beanstalkd", "-p", "11300"]
