FROM ubuntu:latest

RUN \
# Install Web
    apt-get update && \
    apt-get install -y nginx

# Forward request logs to Docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

# Copy all files to site directory
COPY ./files/index.html /var/www/site/index.html

# Add nginx config
ADD ./files/default /etc/nginx/sites-available/default

# Disable ipv6
ADD ./files/ipv6off.sh /etc/rc.local

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]
