FROM rockylinux:9

RUN useradd -m -d /home/app app

RUN dnf install -y git openssh-clients rsync tzdata \
        && dnf clean all \
        && rm -rf /var/cache/dnf/*

WORKDIR /home/app
USER app

