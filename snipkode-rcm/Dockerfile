FROM snipkode/rcm:1.2

# set version label
ARG THEME=Nordic
ARG BUILD_DATE=2023-08-23
ARG VERSION=1.0

LABEL build_version="Snipkode RCM version:- ${VERSION} Build-date:- ${BUILD_DATE}"
LABEL maintainer="snipkode"

ARG DEBIAN_FRONTEND="noninteractive"

RUN \
    echo "**** Install Kvantum Manager ****" && \
    mkdir -p ~/.config/Kvantum && \
    mkdir -p ~/.local/share && \
    chown -R abc:abc ~/.config/Kvantum &&\
    chown -R abc:abc ~/.local/share

RUN \
    echo "**** install packages ****" && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive \
    apt install --no-install-recommends -y \
        git \
        nano \ 
        krfb \
        qt5-style-kvantum \
        curl \
        qt5-style-kvantum-themes \
        mc 

RUN \
    echo "**** Fetch Nordic Theme ****" && \
    mkdir -p ~/git && \
    cd ~/git  && \
    git clone https://gitlab.com/snipkode/Nordic.git && \
    cd Nordic/kde  && \
    cp -a * ~/.local/share/  && \
    mkdir -p ~/.config/Kvantum  && \
    mv ~/.local/share/kvantum/Nordic* ~/.config/Kvantum/ && \
    mv ~/.local/share/colorschemes ~/.local/share/color-schemes && \
    mkdir -p ~/.local/share/aurorae/themes # Window Decorations && \
    mv ~/.local/share/aurorae/Nordic* ~/.local/share/aurorae/themes/
