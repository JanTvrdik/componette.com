# Inherits from official Nginx
FROM nginx:1.9

# Clean image
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Nginx configuration
ADD nginx.conf /etc/nginx/
ADD mime.types /etc/nginx/

# Start Nginx
CMD ["nginx"]
