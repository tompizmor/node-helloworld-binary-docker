FROM bitnami/minideb-extras:jessie-r35
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages ghostscript imagemagick libbz2-1.0 libc6 libgcc1 libmysqlclient18 libncurses5 libreadline6 libsqlite3-0 libssl1.0.0 libstdc++6 libtinfo5 net-tools zlib1g
RUN bitnami-pkg install node-6.14.1-0 --checksum 2746a8deacaed0271fceaa9484ab396e543593fee1a886d193da5c4079ac9d9f
RUN bitnami-pkg unpack canary-binary-1.0.13-0 --checksum f4dd0a7e8799ba1616704a3c98abf6f685fcb1615c5f077ae3bdd8cb2519aa80

COPY rootfs /
ENV BITNAMI_APP_NAME="canary-binary" \
    BITNAMI_IMAGE_VERSION="1.0.13-r10" \
    PATH="/opt/bitnami/node/bin:/opt/bitnami/canary-binary/bin:$PATH"

EXPOSE 8080

ENTRYPOINT ["/app-entrypoint.sh"]
CMD ["nami","start","--foreground","canary-binary"]
