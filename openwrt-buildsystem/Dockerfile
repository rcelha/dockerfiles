FROM buildpack-deps:jessie-curl

RUN apt-get update && \
    apt-get install -y git-core build-essential libssl-dev libncurses5-dev unzip gawk python subversion && \
    apt-get autoremove && \
    apt-get autoclean;

RUN useradd -m developer

WORKDIR /code
RUN chown developer: /code
USER developer

ENV OPENWRT_SOURCE https://codeload.github.com/openwrt/openwrt/tar.gz/v15.05
RUN curl https://codeload.github.com/openwrt/openwrt/tar.gz/v15.05 | tar xzf -
WORKDIR /code/openwrt-15.05
