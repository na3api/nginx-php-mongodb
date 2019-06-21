FROM php:7.2-fpm-alpine

    RUN docker-php-ext-install mysqli pdo pdo_mysql mbstring

RUN apk --update add --virtual build-dependencies build-base openssl-dev autoconf \
  && pecl install mongodb \
  && docker-php-ext-enable mongodb \
  && apk del build-dependencies build-base openssl-dev autoconf \
  && rm -rf /var/cache/apk/

WORKDIR /var/www/project

ADD php.ini /usr/local/etc/php/conf.d/
ADD zz-www.conf /usr/local/etc/php-fpm.d/

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
