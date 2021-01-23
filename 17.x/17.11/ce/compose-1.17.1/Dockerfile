FROM docker:17.11.0-ce

MAINTAINER tim@jtim.nl

ARG DOCKER_COMPOSE_VERSION=1.17.1

RUN apk add --update \
    py-pip \
  && pip install docker-compose==$DOCKER_COMPOSE_VERSION \
  && rm -rf /var/cache/apk/*