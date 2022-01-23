FROM ubuntu:20.04

RUN useradd -m -d /home/app app

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        ssh \
        rsync \
        ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /home/app
USER app
