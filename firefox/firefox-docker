#!/bin/sh

mkdir -p ~/.docker/data/firefox
xhost +
docker run \
       -ti \
       --device=/dev/snd \
       -v ~/.docker/data/firefox:/data  \
       -v /tmp/.X11-unix:/tmp/.X11-unix:ro \
       -v /dev/snd:/dev/snd \
       -e DISPLAY=unix$DISPLAY \
       bitschupser/firefox
