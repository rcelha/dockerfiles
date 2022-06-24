# Usage:
#   docker run -it --rm -v ${HOME}/.tldr:/root/.tldr rcelha/tldr
#

FROM rust:1.61.0-slim-buster
RUN cargo install tealdeer && tldr --update
ENTRYPOINT ["tldr"]
