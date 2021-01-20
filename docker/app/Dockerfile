FROM php:7.4-fpm-alpine

WORKDIR /var/www/app

COPY php.ini /usr/local/etc/php/

RUN apk add --update \
    wget \
    git \
    bash \
    curl \
    vim \
    zip \
    unzip \
    libjpeg-turbo \
    libjpeg-turbo-dev \
    libpng \
    libpng-dev \
    mysql-client \
    openssh
RUN apk add --update --no-cache oniguruma-dev

RUN git clone -b 5.2.2 https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis

RUN docker-php-ext-install pdo mbstring pdo_mysql exif redis
#RUN docker-php-ext-configure gd --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ && \
#    docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) gd
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/app

ENV COMPOSER_ALLOW_SUPERUSER 1
