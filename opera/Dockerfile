FROM ubuntu:xenial

RUN apt-get update && \
    apt-get install -y wget && \
    wget -O opera.deb "http://download2.operacdn.com/pub/opera-developer/39.0.2248.0/linux/opera-developer_39.0.2248.0_amd64.deb" && \
    apt-get install -y ./opera.deb;

ENTRYPOINT ["opera-developer"]
