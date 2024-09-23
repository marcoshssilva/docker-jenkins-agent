FROM jenkins/inbound-agent as jenkins

USER root

ARG BUILDX_VERSION=v0.17.1
ARG DOCKER_VERSION=27.3.1

RUN apt update && apt install -y curl jq tar gzip && \
    curl -Lo /usr/local/bin/docker-buildx "https://github.com/docker/buildx/releases/download/$BUILDX_VERSION/buildx-$BUILDX_VERSION.linux-$(uname -m)" && \
    curl -Lo docker.tgz "https://download.docker.com/linux/static/stable/$(uname -m)/docker-$DOCKER_VERSION.tgz" && \
    chmod +x /usr/local/bin/docker-buildx && \
    tar -xvf docker.tgz && \
    mv docker/* /usr/local/bin/ && \
    rm -rf docker