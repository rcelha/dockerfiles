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

WORKDIR /scala-2.11.8/bin

CMD ["./scala"]
