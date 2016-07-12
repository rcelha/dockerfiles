FROM buildpack-deps:jessie-curl

WORKDIR /terraform
RUN set -ex ;\
    apt update; \
    apt install -y unzip; \
    curl -o terraform.zip https://releases.hashicorp.com/terraform/0.6.16/terraform_0.6.16_linux_amd64.zip; \
    unzip -x terraform.zip; \
    rm terraform.zip;

ENV PATH /terraform:$PATH

WORKDIR /code
VOLUME /code

ENTRYPOINT ["terraform"]
CMD ["--help"]
