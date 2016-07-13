FROM rcelha/scala:sbt

ONBUILD COPY . /code
WORKDIR /code
ONBUILD RUN sbt compile

VOLUME ['/code', '/root/.sbt', '/root/.ivy2']
CMD ["sbt"]
