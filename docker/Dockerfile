FROM ubuntu:18.04
MAINTAINER "chataro0 <chataro012@gmail.com>"

ENV PACKER_VERSION=1.3.1
ENV PACKER_SHA256SUM=254cf648a638f7ebd37dc1b334abe940da30b30ac3465b6e0a9ad59829932fa3

RUN apt update \
 && apt install -y openssl ssh unzip ansible \
 && rm -rf /var/lib/apt/lists/*

ADD https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip ./
ADD https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_SHA256SUMS ./

RUN sed -i '/.*linux_amd64.zip/!d' packer_${PACKER_VERSION}_SHA256SUMS
RUN sha256sum -c packer_${PACKER_VERSION}_SHA256SUMS
RUN unzip packer_${PACKER_VERSION}_linux_amd64.zip -d /bin
RUN rm -f packer_${PACKER_VERSION}_linux_amd64.zip
