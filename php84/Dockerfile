FROM alpine:3.24

RUN apk update \
  && apk upgrade --available --prune \
  && apk add --no-cache \
    git \
    php84 \
    php84-bcmath \
    php84-calendar \
    php84-ctype \
    php84-curl \
    php84-dom \
    php84-gd \
    php84-fileinfo \
    php84-fpm \
    php84-iconv \
    php84-intl \
    php84-mbstring \
    php84-mysqli \
    php84-opcache \
    php84-openssl \
    php84-pdo \
    php84-pdo_mysql \
    php84-pdo_sqlite \
    php84-pecl-xdebug \
    php84-phar \
    php84-session \
    php84-simplexml \
    php84-tokenizer \
    php84-xml \
    php84-xmlwriter \
    php84-xmlreader \
    php84-zip \
    sqlite \
  && rm -rf /var/cache/apk/*

RUN ln -sf /usr/bin/php84 /usr/bin/php
RUN echo "zend_extension=xdebug.so" >> /etc/php84/conf.d/50_xdebug.ini \
  && echo "xdebug.mode=coverage" >> /etc/php84/conf.d/50_xdebug.ini

# Composer is not installed with apk because it installs php8 and uses that as the default version.
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
