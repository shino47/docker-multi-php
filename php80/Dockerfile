FROM alpine:3.16

RUN apk update \
  && apk upgrade --available --prune \
  && apk add --no-cache \
    git \
    composer \
    php8 \
    php8-ctype \
    php8-curl \
    php8-dom \
    php8-gd \
    php8-fileinfo \
    php8-fpm \
    php8-iconv \
    php8-intl \
    php8-mbstring \
    php8-mysqli \
    php8-opcache \
    php8-openssl \
    php8-pdo \
    php8-pdo_mysql \
    php8-phar \
    php8-session \
    php8-simplexml \
    php8-tokenizer \
    php8-xml \
    php8-xmlwriter \
    php8-xmlreader \
    php8-zip \
  && rm -rf /var/cache/apk/*
