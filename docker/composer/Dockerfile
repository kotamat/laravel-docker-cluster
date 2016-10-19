FROM php:7.0.12

MAINTAINER "Kota Matsumoto" <kota1861@gmail.com>

WORKDIR /tmp

RUN apt-get update -y
RUN apt-get install -y git unzip
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN composer self-update
RUN composer global require hirak/prestissimo

RUN mkdir -p /data/www
VOLUME ["/data"]
WORKDIR /data/www

ENTRYPOINT ["composer"]
CMD ["--help"]
