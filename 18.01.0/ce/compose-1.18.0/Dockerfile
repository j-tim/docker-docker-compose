FROM docker:18.01.0-ce

MAINTAINER tim@jtim.nl

ARG DOCKER_COMPOSE_VERSION=1.18.0

RUN apk add --update \
    py-pip \
  && pip install docker-compose==$DOCKER_COMPOSE_VERSION \
  && rm -rf /var/cache/apk/*