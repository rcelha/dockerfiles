FROM alpine

RUN set -ex ;\
    apk update ;\
    apk add openjdk8 bash openssl;

ENV SBT_VERSION 0.13.11
ENV SBT_URL https://dl.bintray.com/sbt/native-packages/sbt/$SBT_VERSION/sbt-$SBT_VERSION.tgz
RUN set -ex ;\
    wget $SBT_URL ;\
    tar -xvzf sbt-$SBT_VERSION.tgz ;\
    rm sbt-$SBT_VERSION.tgz;

ENV SBT_HOME /sbt
ENV PATH $PATH:$SBT_HOME/bin

WORKDIR /code
CMD ["sbt", "run"]
