# Base image
FROM bitnami/minideb:latest

# Maintaner
MAINTAINER Tommy Crestanello -

# install_packages
RUN install_packages apache2 memcached telnet wget net-tools nginx nano curl

# Removing the configuration file
RUN rm -v /etc/nginx/nginx.conf

# Create a new configuration file
ADD nginx.conf /etc/nginx

# install_packages
RUN install_packages php nodejs

ENV BITNAMI_PKG_CHMOD="-R g+rwX" \
    BITNAMI_PKG_EXTRA_DIRS="/bitnami/mariadb/conf" \
    HOME="/"

# Install required system packages and dependencies
RUN install_packages libaio1 libc6 libgcc1 libjemalloc1 libncurses5 libstdc++6 libtinfo5 zlib1g gnupg2 gnupg1
# RUN bitnami-pkg unpack mariadb-10.1.30-1 --checksum 95a2b2c55051d2babb34d950d161272a1da80c98460a15e84f7fbd77d4455b36

# RUN apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 0xF1656F24C74CD1D8
RUN add-apt-repository 'deb [arch=amd64,i386] http://www.ftp.saix.net/DB/mariadb/repo/10.1/debian sid main'

RUN apt-get update
RUN apt-get install mariadb-server

COPY rootfs /

ENV ALLOW_EMPTY_PASSWORD="no" \
    BITNAMI_APP_NAME="mariadb" \
    BITNAMI_IMAGE_VERSION="10.1.30-r1" \
    MARIADB_DATABASE="" \
    MARIADB_MASTER_HOST="" \
    MARIADB_MASTER_PORT_NUMBER="" \
    MARIADB_MASTER_ROOT_PASSWORD="" \
    MARIADB_MASTER_ROOT_USER="" \
    MARIADB_PASSWORD="" \
    MARIADB_PORT_NUMBER="3306" \
    MARIADB_REPLICATION_MODE="" \
    MARIADB_REPLICATION_PASSWORD="" \
    MARIADB_REPLICATION_USER="" \
    MARIADB_ROOT_PASSWORD="" \
    MARIADB_ROOT_USER="root" \
    MARIADB_USER="" \
    PATH="/opt/bitnami/mariadb/bin:/opt/bitnami/mariadb/sbin:$PATH"

EXPOSE 8888:80 3306

USER 1001

CMD service nginx start

CMD ["/bin/bash"]
