FROM php:7.2.7-fpm-alpine3.7
RUN apk update \
    apk upgrade;

#install some basic tools
RUN apk add \
        git \
        tree \
        vim \
        wget \
        zip \
        unzip \
        php7-zip \
        subversion;

#install some base extensions
RUN apk add \
        zlib-dev \
        zip \
  && docker-php-ext-install zip mysqli pdo pdo_mysql

#setup composer
RUN curl -sS https://getcomposer.org/installer | php \
        && mv composer.phar /usr/local/bin/ \
        && ln -s /usr/local/bin/composer.phar /usr/local/bin/composer


WORKDIR /var/www/