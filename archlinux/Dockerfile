FROM base/archlinux
MAINTAINER Alexander Rampp <dev@axgr.de>

ADD mirrorlist /etc/pacman.d/mirrorlist

## Base packages
RUN pacman-key --populate archlinux && \
    pacman-key --refresh-keys

RUN pacman -Sy --noconfirm && \
    pacman -S pacman openssl --noconfirm && \
    pacman-db-upgrade

RUN pacman -Syyu --needed --noconfirm
