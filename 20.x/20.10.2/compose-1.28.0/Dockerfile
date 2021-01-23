# https://hub.docker.com/_/docker
# https://docs.docker.com/release-notes/
FROM docker:20.10.2-git

MAINTAINER tim@jtim.nl

ARG DOCKER_COMPOSE_VERSION=1.28.0
ARG PACK_VERSION=v0.16.0

ENV USERNAME=bob-the-builder

RUN apk add --update \
    # https://wiki.alpinelinux.org/wiki/Docker#Docker_Compose
    py-pip sshpass openssh-client python3-dev libffi-dev openssl-dev gcc libc-dev make jq curl && \
    pip install --no-cache-dir docker-compose==$DOCKER_COMPOSE_VERSION && \
    (curl -sSL "https://github.com/buildpacks/pack/releases/download/$PACK_VERSION/pack-$PACK_VERSION-linux.tgz" | tar -C /usr/local/bin/ --no-same-owner -xzv pack) && \
    rm -rf /var/cache/apk/*

RUN addgroup -g 1000 -S ${USERNAME} && \
    adduser -u 1000 -S ${USERNAME} -G ${USERNAME}

USER ${USERNAME}