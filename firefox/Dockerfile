FROM bitschupser/archlinux-de
MAINTAINER Alexander Rampp <dev@axgr.de>

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

USER user

CMD ["firefox", "--profile", "/data", "--new-instance"]
