#############################################################
#
# Dockerfile to build Nginx Installed inside a Containers
#
#############################################################

# Set the base image to Ubuntu
FROM ubuntu

# File Author / Maintaner
MAINTAINER Tommy Crestanello

# Update the repository of all installation packages
RUN apt-get update

# Resolving and installig all tools for Nginx
RUN apt-get install -y nano wget dialog net-tools

# Download and install Nginx web-server
RUN apt-get install -y nginx

# Removing the configuration file
RUN rm -v /etc/nginx/nginx.conf

# Create a new configuration file
ADD nginx.conf /etc/nginx

# Exposing port
EXPOSE 80

# End command starting the nginx service
# CMD service nginx start
CMD ["/bin/bash"]
