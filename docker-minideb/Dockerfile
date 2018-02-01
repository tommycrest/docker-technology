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

EXPOSE 8888:80

CMD service nginx start

CMD ["/bin/bash"]
