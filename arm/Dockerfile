FROM hypriot/rpi-node:slim
MAINTAINER Bas Bloembergen <basbloembergen@gmail.com>

ARG VERSION

RUN apt-get update && apt-get install -y curl wget libavahi-compat-libdnssd-dev dbus avahi-daemon node-gyp make g++ build-essential avahi-discover libnss-mdns

RUN sed -i.bak 's/^#enable-dbus/enable-dbus/' /etc/avahi/avahi-daemon.conf

RUN npm install -g homebridge homebridge-homeassistant@${VERSION}

USER root

VOLUME /root

EXPOSE 5353 51826

ENTRYPOINT ["/bin/sh", "/root/run.sh"]
