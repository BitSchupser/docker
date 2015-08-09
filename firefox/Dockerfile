FROM base/archlinux
MAINTAINER Alexander Rampp <dev@axgr.de>

## Base packages
RUN pacman-key --populate archlinux && \
    pacman-key --refresh-keys

RUN pacman -Sy --noconfirm && \
    pacman -S pacman openssl --noconfirm && \
    pacman-db-upgrade

RUN pacman -Syyu --needed --noconfirm

RUN pacman -S --noconfirm firefox \
                          firefox-i18n-de \
                          firefox-adblock-plus \
                          arch-firefox-search \
                          xorg-fonts-100dpi

RUN useradd -d /home/user -m user

RUN mkdir /data && \
    chown user:user /data && \
    touch /data/init_volume

VOLUME /data

#USER user

CMD ["firefox", "--profile", "/data", "--new-instance"]
