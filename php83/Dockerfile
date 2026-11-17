FROM alpine:3.24

RUN apk update \
  && apk upgrade --available --prune \
  && apk add --no-cache \
    git \
    php83 \
    php83-ctype \
    php83-curl \
    php83-dom \
    php83-gd \
    php83-fileinfo \
    php83-fpm \
    php83-iconv \
    php83-intl \
    php83-mbstring \
    php83-mysqli \
    php83-opcache \
    php83-openssl \
    php83-pdo \
    php83-pdo_mysql \
    php83-pdo_sqlite \
    php83-pecl-xdebug \
    php83-phar \
    php83-session \
    php83-simplexml \
    php83-tokenizer \
    php83-xml \
    php83-xmlwriter \
    php83-xmlreader \
    php83-zip \
    sqlite \
  && rm -rf /var/cache/apk/*

RUN ln -sf /usr/bin/php83 /usr/bin/php
RUN echo "zend_extension=xdebug.so" >> /etc/php83/conf.d/50_xdebug.ini \
  && echo "xdebug.mode=coverage" >> /etc/php83/conf.d/50_xdebug.ini

# Composer is not installed with apk because it installs php85 and uses that as the default version.
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
