FROM ubuntu:xenial

RUN apt-get update && \
    apt-get install -y wget chromium-codecs-ffmpeg-extra && \
    wget -O opera.deb "http://download2.operacdn.com/pub/opera-developer/39.0.2248.0/linux/opera-developer_39.0.2248.0_amd64.deb" && \
    apt-get install -y ./opera.deb;

ENV OPERA_USER_AGENT "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.84 Safari/537.36"
ENTRYPOINT opera-developer --user-agent="${OPERA_USER_AGENT}"
