FROM rockylinux:9

# https://github.com/gohugoio/hugo/releases/tag/v0.111.3
ENV HUGO_URL='https://github.com/gohugoio/hugo/releases/download/v0.111.3/hugo_extended_0.111.3_linux-amd64.tar.gz' \
    HUGO_CHECKSUM='b382aacb522a470455ab771d0e8296e42488d3ea4e61fe49c11c32ec7fb6ee8b'

RUN dnf install -y git openssh-clients rsync tzdata \
        && cd /root \
        && curl -L -o hugo.tar.gz "${HUGO_URL}" \
        && echo "${HUGO_CHECKSUM}  hugo.tar.gz" | sha256sum -c - \
        && tar zxvf hugo.tar.gz \
        && mv hugo /usr/local/bin/hugo \
        && rm hugo.tar.gz \
        && dnf clean all \
        && rm -rf /var/cache/dnf/* \
        && mkdir /app

WORKDIR /app

