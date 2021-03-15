# Run present (https://pypi.org/project/present/)
#
# docker run -it --rm
#            -v ${HOME}/Documents:/root/Documents
#            rcelha/present
#

ARG PYTHON_VERSION=3.9.2
ARG PRESENT_VERSION=0.6.0

FROM python:${PYTHON_VERSION}-slim

ARG PRESENT_VERSION
RUN pip install present==${PRESENT_VERSION}

ENTRYPOINT ["present"]
