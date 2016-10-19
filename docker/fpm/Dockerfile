FROM php:7.0.12-fpm

MAINTAINER "Kota Matsumoto" <kota1861@gmail.com>

RUN apt-get update -y

# clean fpm conf
# RUN rm /usr/local/etc/php-fpm.d/*
COPY php-fpm.d /usr/local/etc/php-fpm.d

RUN mkdir -p /data
VOLUME ["/data"]
