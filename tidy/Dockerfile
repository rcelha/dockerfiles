FROM ubuntu:latest

ADD http://binaries.html-tidy.org/binaries/tidy-5.2.0/tidy-5.2.0-64bit.deb /tmp/tidy-5.2.0-64bit.deb
RUN set -ex;\
    dpkg -i /tmp/tidy-5.2.0-64bit.deb;

ENTRYPOINT ["/usr/bin/tidy"]
CMD ["--help"]
