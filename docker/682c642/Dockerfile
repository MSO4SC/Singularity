# Dockerfile for Singularity 2.4

FROM ubuntu:xenial
MAINTAINER Victor Sande <vsande@cesga.es>

RUN apt-get update \
    && apt-get install -y \
        curl git make uuid-dev libssl-dev libarchive-dev autoconf automake libtool  \
        tar gzip bash python e2fsprogs squashfs-tools \
    && cd /tmp \
    && git clone https://github.com/dctrud/singularity.git \
    && cd /tmp/singularity \
    && git checkout 682c642  \
    && ./autogen.sh \
    && ./configure --prefix=/usr/local \
    && make \
    && make install \
    && cd /tmp \
    && rm -rf /tmp/singularity \
    && apt-get remove --purge -y curl git make autoconf automake libtool 
