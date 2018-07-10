FROM docker:18.05.0-ce-git

MAINTAINER tim@jtim.nl

ARG DOCKER_COMPOSE_VERSION=1.21.2

ENV USERNAME=bob-the-builder

RUN apk add --update \
    py-pip \
  && pip install docker-compose==$DOCKER_COMPOSE_VERSION \
  && rm -rf /var/cache/apk/*

RUN addgroup -g 1000 -S ${USERNAME} && \
    adduser -u 1000 -S ${USERNAME} -G ${USERNAME}

USER ${USERNAME}