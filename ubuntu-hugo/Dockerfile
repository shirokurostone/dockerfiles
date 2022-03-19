FROM ubuntu:20.04

# https://github.com/gohugoio/hugo/releases/tag/v0.94.2
ENV HUGO_URL='https://github.com/gohugoio/hugo/releases/download/v0.94.2/hugo_extended_0.94.2_Linux-64bit.deb' \
    HUGO_CHECKSUM='88b7fa12eb843d6fc08e94b2bb0e47902843a803b52286bb7b74b2121b892fb2'

RUN cd /root && \
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y curl git tzdata && \
    curl -L -o hugo.deb "$HUGO_URL" && \
    echo "$HUGO_CHECKSUM  hugo.deb" | sha256sum -c - && \
    dpkg -i hugo.deb && rm hugo.deb && \
    useradd -d /app -s /bin/sh -u 1000 app && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

