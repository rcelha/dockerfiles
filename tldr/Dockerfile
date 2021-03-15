# Usage:
#   docker run -it --rm -v ${HOME}/.tldr:/root/.tldr rcelha/tldr
#

FROM node:lts-buster-slim
RUN npm i -g tldr
ENTRYPOINT ["tldr"]
