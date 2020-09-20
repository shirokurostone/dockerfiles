FROM alpine:3.12.0

# https://github.com/gohugoio/hugo/releases/tag/v0.75.1
ENV HUGO_URL='https://github.com/gohugoio/hugo/releases/download/v0.75.1/hugo_0.75.1_Linux-64bit.tar.gz' \
    HUGO_CHECKSUM='98e157dc2eda1f78b19959ff45c8a750abd6ae12330fad6574b466efdb58bd1d'

RUN apk add --no-cache git tzdata && \
    mkdir /work && cd /work && \
    wget "$HUGO_URL" -O hugo.tar.gz && \
    echo "$HUGO_CHECKSUM  hugo.tar.gz" | sha256sum -c - && \
    tar zxvf hugo.tar.gz && \
    mv hugo /usr/local/bin && \
    cd / && rm -r /work && \
    adduser -h /app -s /bin/sh -u 1000 -S app

# USER app
WORKDIR /app

