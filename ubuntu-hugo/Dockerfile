FROM ubuntu:20.04

# https://github.com/gohugoio/hugo/releases/tag/v0.85.0
ENV HUGO_URL='https://github.com/gohugoio/hugo/releases/download/v0.85.0/hugo_extended_0.85.0_Linux-64bit.deb' \
    HUGO_CHECKSUM='81ecc8eb0dee6e9df85b2cb9c58162ec05f8fc47b308540379d9a5c87f8b7476'

RUN cd /root && \
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y curl git tzdata && \
    curl -L -o hugo.deb "$HUGO_URL" && \
    echo "$HUGO_CHECKSUM  hugo.deb" | sha256sum -c - && \
    dpkg -i hugo.deb && rm hugo.deb && \
    useradd -d /app -s /bin/sh -u 1000 app && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

