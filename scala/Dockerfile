FROM alpine

RUN set -ex ;\
    apk update ;\
    apk add openjdk8 ;\
    apk add bash;

ENV SCALA_URL http://downloads.lightbend.com/scala/2.11.8/scala-2.11.8.tgz
RUN set -ex ;\
    wget $SCALA_URL ;\
    tar -xvzf scala-2.11.8.tgz ;\
    rm scala-2.11.8.tgz;

ENV SCALA_HOME /scala-2.11.8
ENV PATH $PATH:$SCALA_HOME/bin

WORKDIR /code
VOLUME ['/code']
CMD ["scala"]
