# Create an image from existing nging latest
FROM nginx

# The startup scripting will be copied on /
COPY startup-nginx-app.sh /

# Copy all html folder in delivery folder of nginx
COPY html /usr/share/nginx/html

# on startup of nginx docker images launch the command on shell scripting
CMD ["./startup-nginx-app.sh"]
