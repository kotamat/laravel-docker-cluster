FROM debian:jessie

MAINTAINER "Kota Matsumoto" <kota1861@gmail.com>

RUN apt-get update -y
RUN apt-get install -y curl git
RUN curl -sL https://deb.nodesource.com/setup | bash --
RUN apt-get install -y nodejs

RUN npm update -g npm
RUN npm i -g gulp-cli

RUN mkdir -p /data/www
VOLUME ["/data"]
WORKDIR /data/www

ENTRYPOINT ["gulp"]
CMD ["-h"]
