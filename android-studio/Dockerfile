FROM buildpack-deps:jessie-curl

MAINTAINER Rodrigo <rcelha@gmail.com>

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
            unzip \
            openjdk-7-jdk \
            lib32stdc++6 \
            gradle;
RUN apt-get clean
RUN apt-get purge

ENV URL_STUDIO https://dl.google.com/dl/android/studio/ide-zips/1.5.1.0/android-studio-ide-141.2456560-linux.zip
RUN curl "${URL_STUDIO}" > /tmp/studio.zip && unzip -d /opt /tmp/studio.zip && rm /tmp/studio.zip

ENV UNAME developer
RUN useradd -m ${UNAME};
USER ${UNAME}

CMD /opt/android-studio/bin/studio.sh
