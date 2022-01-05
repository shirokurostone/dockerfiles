FROM ubuntu:20.04

# https://github.com/gohugoio/hugo/releases/tag/v0.91.2
ENV HUGO_URL='https://github.com/gohugoio/hugo/releases/download/v0.91.2/hugo_extended_0.91.2_Linux-64bit.deb' \
    HUGO_CHECKSUM='a7480201ec1e32f7fc0c0346234fa8f80cea9b9945a33809e984addd1ef322fb'

RUN cd /root && \
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y curl git tzdata && \
    curl -L -o hugo.deb "$HUGO_URL" && \
    echo "$HUGO_CHECKSUM  hugo.deb" | sha256sum -c - && \
    dpkg -i hugo.deb && rm hugo.deb && \
    useradd -d /app -s /bin/sh -u 1000 app && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

