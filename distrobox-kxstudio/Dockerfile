FROM ubuntu:21.10

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt install -y wget && apt autoclean && apt autoremove

ENV WINEHQ_REPO=impish

## Wine
RUN dpkg --add-architecture i386 && \
    wget -nc https://dl.winehq.org/wine-builds/winehq.key && \
    mv winehq.key /usr/share/keyrings/winehq-archive.key && \
    wget -nc https://dl.winehq.org/wine-builds/ubuntu/dists/impish/winehq-${WINEHQ_REPO}.sources && \
    mv winehq-impish.sources /etc/apt/sources.list.d/ && \
    apt update && \
    apt install --install-recommends -y winehq-stable && \
    apt autoclean && apt autoremove

ENV KXSTUDIO_VERSION=11.1.0
ENV KXSTUDIO_REPO_FILE=kxstudio-repos_${KXSTUDIO_VERSION}_all.deb

## KXStudio
RUN apt update && \
    apt install -y apt-transport-https gpgv wget && \
    wget https://launchpad.net/~kxstudio-debian/+archive/kxstudio/+files/${KXSTUDIO_REPO_FILE} && \
    dpkg -i ${KXSTUDIO_REPO_FILE} && \
    apt update && \
    apt install --yes carla cadence cadence-tools wineasio carla-bridge-win32 carla-bridge-win64 && \
    apt autoclean && apt autoremove && rm ${KXSTUDIO_REPO_FILE}

# sudo usermod -aG audio $(whoami)
# Wine + asio + wineasio
# wineboot
# wine64 regsvr32 /opt/wine-staging/lib64/wine/x86_64-windows/wineasio.dll
