FROM ubuntu:14.04

MAINTAINER ricardo@droboports.com

ENV USER_ID 1000
ENV GROUP_ID 1000

RUN set -x; \
    apt-get -y update && \
    apt-get -y upgrade && \
    apt-get -y install build-essential realpath wget gawk && \
    apt-get clean && \
    apt-get autoclean

RUN set -x; \
    groupadd -r -g $GROUP_ID drobo && \
    useradd -r -u $USER_ID -g drobo -G sudo drobo && \
    echo drobo:drobo | chpasswd

RUN set -x; \
    mkdir -p /home/drobo/build && \
    chown -R drobo:drobo /home/drobo

VOLUME ["/home/drobo/build"]

USER drobo
