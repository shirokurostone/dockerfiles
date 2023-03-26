FROM rockylinux:9

RUN dnf install -y git openssh-clients rsync tzdata \
        && dnf clean all \
        && rm -rf /var/cache/dnf/* \
        && mkdir /app

WORKDIR /app

