FROM docker:17.07.0-ce

MAINTAINER tim@jtim.nl

ARG DOCKER_COMPOSE_VERSION=1.16.1

RUN apk add --update \
    py-pip \
  && pip install docker-compose==$DOCKER_COMPOSE_VERSION \
  && rm -rf /var/cache/apk/*