ARG BUILD_FROM

FROM $BUILD_FROM as build
ARG BUILD_VERSION=latest

RUN apk add --no-cache nodejs npm python3 make g++ linux-headers libusb-dev eudev-dev avahi-dev
RUN npm install -g --unsafe-perm room-assistant@$BUILD_VERSION

FROM $BUILD_FROM

WORKDIR /room-assistant
ENV LANG C.UTF-8

RUN apk add --no-cache nodejs npm bluez bluez-deprecated libusb avahi-dev bind-tools dmidecode \
    && setcap cap_net_raw+eip $(eval readlink -f `which node`) \
    && setcap cap_net_raw+eip $(eval readlink -f `which hcitool`) \
    && setcap cap_net_admin+eip $(eval readlink -f `which hciconfig`) \
    && mkdir -p /room-assistant/config \
    && ln -s /data/options.json /room-assistant/config/local.json \
    && ln -s /usr/lib/node_modules/room-assistant/bin/room-assistant.js /usr/bin/room-assistant

COPY rootfs /
COPY --from=build /usr/lib/node_modules/room-assistant /usr/lib/node_modules/room-assistant

CMD ["/room-assistant/entrypoint.sh"]