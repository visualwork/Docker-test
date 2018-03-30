FROM ubuntu:16.04
MAINTAINER sanjuk <test@anonymouse.com>

RUN apt-get update
RUN apt-get install -y nginx
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf
RUN chown -R www-data:www-data /var/lib/nginx


VOLUME /data

WORKDIR /etc/nginx

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
