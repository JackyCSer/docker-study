FROM ubuntu:14.04
MAINTAINER Jacky "jacky_cser@yeah.net"
ENV REFRESHED_AT 2016-10-28
RUN apt-get -yqq update && apt-get -yqq install nginx
RUN mkdir -p /var/www/html/website
ADD nginx/global.conf /etc/nginx/conf.d/
ADD nginx/nginx.conf /etc/nginx/nginx.conf
EXPOSE 80


