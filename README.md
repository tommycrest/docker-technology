# DOCKER TECHNOLOGY - Explore containers
----------------------------------------

A little git with some technology exploration on containers technology based on Docker
with some example.

Have a lot of fun!

- docker-nginx-static-app : delivery of static page from nginx.

	- docker build -t "images-name-placeholder" .
	- docker run --name "nginx-container-placeholder" -d -p 80080:80 "images-name-placeholder"
	- from browser: http://localhost:8080 or http://host-ip:8080

- docker-ubuntu-nginx :

  	- script for the creation of a container with ubuntu and nginx web-server configured to expose port 80.

- docker-minideb :

	- docker image derived from bitnami/minideb with some additional installed packages
	[ apache2 memcached telnet wget net-tools nginx nano curl php nodejs ]

	- How to use this Dockerfile: 
		+ docker build -t "image-name-placeholder" . [building the image by reading the local Dockerfile]
		+ docker run --name "container-name-placeholder" -p 8888:80 -i -t "image-name-placeholder" [run the container]
 
	The container via Dockerfile launch the following command : service nginx start

	for starting immediately the webserver Nginx on the expose port: EXPOSE 8888:80

	that map the port 8888 to internal port 80 on the container.

	Now you can access from your browser the following url: http://localhost:8888/
 
