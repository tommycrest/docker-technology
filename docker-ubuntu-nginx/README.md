# #######################################################
# Ubuntu containers images with Nginx
# #######################################################

How To use the code inside this folder:

1. Launch the docker command for building the image:

    docker build -t "choose-images-name" .

2. Launch the docker command for container's creation:

    docker run --name "choose-containers-name" -p 80:80 -i -t  "choose-images-name"

On the Dockerfile are describe all the instruction that permit to install nginx on Ubuntu container.

With these 2 command the containers return:

1. CMD service nginx start : immediately start the nginx service
2. CMD ["/bin/bash"]       : return directly the bash prompt

If during the container creation choose the operation number (2.) it's important to remember
to launch from bash the following command:

  service nginx start

or use directly from bash prompt the following command:

  exec nginx -g "daemon off;"


TECHNICAL NOTE: Inside the dockerfil I commented the following line:

  # COPY html /usr/share/nginx/html

If you already have a static application to deploy de-commented the line.

Have a lot of fun!
