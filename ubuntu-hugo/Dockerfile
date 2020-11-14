FROM ubuntu:20.04

# https://github.com/gohugoio/hugo/releases/tag/v0.78.2
ENV HUGO_URL='https://github.com/gohugoio/hugo/releases/download/v0.78.2/hugo_extended_0.78.2_Linux-64bit.deb' \
    HUGO_CHECKSUM='422261f12880c01968e7436be995526136dc880745e8b8c55401bc819488fb08'

RUN cd /root && \
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y curl git tzdata && \
    curl -L -o hugo.deb "$HUGO_URL" && \
    echo "$HUGO_CHECKSUM  hugo.deb" | sha256sum -c - && \
    dpkg -i hugo.deb && rm hugo.deb && \
    useradd -d /app -s /bin/sh -u 1000 app && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

