# jq
#
# docker run -it --rm
#            -v ${HOME}/Documents:/root/Documents
#            rcelha/jq
#

FROM debian:bullseye-slim
RUN apt update && apt install -y jq
ENTRYPOINT ["jq"]
