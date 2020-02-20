ARG BUILD_FROM

FROM node:12-alpine as build
ARG BUILD_VERSION=latest

RUN apk add --no-cache python make g++ libusb-dev eudev-dev avahi-dev
RUN npm install -g --unsafe-perm room-assistant@$BUILD_VERSION

FROM $BUILD_FROM

WORKDIR /room-assistant
ENV LANG C.UTF-8

RUN apk add --no-cache nodejs npm bluez bluez-deprecated libusb avahi avahi-dev dmidecode \
    && setcap cap_net_raw+eip $(eval readlink -f `which node`) \
    && setcap cap_net_raw+eip $(eval readlink -f `which hcitool`) \
    && mkdir -p /room-assistant/config \
    && ln -s /data/options.json /room-assistant/config/local.json \
    && ln -s /usr/local/lib/node_modules/room-assistant/bin/room-assistant.js /usr/local/bin/room-assistant

COPY rootfs /
COPY --from=build /usr/local/lib/node_modules/room-assistant /usr/local/lib/node_modules/room-assistant

CMD ["/room-assistant/entrypoint.sh"]