# Usage:
#   docker run -it --rm
#          -v ${PWD}:/code
#          rcelha/terraform
#

FROM debian:buster-slim

RUN apt-get update && \
    apt-get install -y curl unzip && \
    rm -rf /var/lib/apt/lists/*

ENV TERRAFORM_VERSION 0.6.16
ENV TERRAFORM_URL https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip
WORKDIR /opt/terraform
RUN curl -o terraform.zip ${TERRAFORM_URL} && \
    ls -lha && \
    unzip -x terraform.zip && \
    rm terraform.zip

ENV PATH /opt/terraform:$PATH

WORKDIR /code
VOLUME /code

ENTRYPOINT ["terraform"]
CMD ["--help"]
