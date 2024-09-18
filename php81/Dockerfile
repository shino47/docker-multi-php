FROM alpine:3.19

RUN apk update \
  && apk upgrade --available --prune \
  && apk add --no-cache \
    git \
    php81 \
    php81-ctype \
    php81-curl \
    php81-dom \
    php81-gd \
    php81-fileinfo \
    php81-fpm \
    php81-iconv \
    php81-intl \
    php81-mbstring \
    php81-mysqli \
    php81-opcache \
    php81-openssl \
    php81-pdo \
    php81-pdo_mysql \
    php81-pdo_sqlite \
    php81-pecl-xdebug \
    php81-phar \
    php81-session \
    php81-simplexml \
    php81-tokenizer \
    php81-xml \
    php81-xmlwriter \
    php81-xmlreader \
    php81-zip \
    sqlite \
  && rm -rf /var/cache/apk/*

RUN ln -sf /usr/bin/php81 /usr/bin/php
RUN echo "zend_extension=xdebug.so" >> /etc/php81/conf.d/50_xdebug.ini \
  && echo "xdebug.mode=coverage" >> /etc/php81/conf.d/50_xdebug.ini

# Composer is not installed with apk because it installs php8 and uses that as the default version.
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
