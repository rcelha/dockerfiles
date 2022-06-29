# prettier
#
# docker run -it --rm
#            -v ${HOME}/Documents:/root/Documents
#            rcelha/prettier
#

FROM node:lts

RUN npm install -g prettier
WORKDIR /plugins

RUN npm install prettier-plugin-sort-json
WORKDIR /code

ENTRYPOINT ["prettier"]
