FROM docker:17.04.0

MAINTAINER tim@jtim.nl

ARG DOCKER_COMPOSE_VERSION=1.12.0

RUN apk add --update \
    py-pip \
  && pip install docker-compose==$DOCKER_COMPOSE_VERSION \
  && rm -rf /var/cache/apk/*