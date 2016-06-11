FROM alpine

RUN apk update && \
    apk add mesa-gl \
            libexif \
            udev \
            ttf-freefont \
            chromium;

ENTRYPOINT ["chromium-browser"]
