FROM php:7.0.12

MAINTAINER "Kota Matsumoto" <kota1861@gmail.com>

WORKDIR /tmp

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        git \
        unzip \
    && docker-php-ext-install -j$(nproc) iconv mcrypt pdo pdo_mysql \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN composer self-update
RUN composer global require hirak/prestissimo

RUN mkdir -p /data
VOLUME ["/data"]
WORKDIR /data

