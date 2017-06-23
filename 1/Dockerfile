FROM bitnami/minideb-extras:jessie-r17
LABEL maintainer "Bitnami <containers@bitnami.com>"



# Install required system packages and dependencies
RUN install_packages ghostscript imagemagick libbz2-1.0 libc6 libgcc1 libmysqlclient18 libncurses5 libreadline6 libsqlite3-0 libssl1.0.0 libstdc++6 libtinfo5 net-tools zlib1g
RUN bitnami-pkg install node-6.11.0-0 --checksum 203d22e3357eb5e8573c8d95691f01e1a2a3badcfc2baee0bf83b3ad91dfeb86
RUN bitnami-pkg unpack canary-binary-1.0.10-0 --checksum 370b669f7504095140817b451d35b0953bae21217ff629f708677025b4b16ede

COPY rootfs /

ENV BITNAMI_APP_NAME="canary-binary" \
    BITNAMI_IMAGE_VERSION="1.0.10-r0" \
    PATH="/opt/bitnami/node/bin:/opt/bitnami/canary-binary/bin:$PATH"



VOLUME ["/bitnami/canary-binary"]

EXPOSE 8080

ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["nami","start","--foreground","canary-binary"]
