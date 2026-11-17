FROM alpine:3.22

RUN apk update \
  && apk upgrade --available --prune \
  && apk add --no-cache \
    git \
    php82 \
    php82-ctype \
    php82-curl \
    php82-dom \
    php82-gd \
    php82-fileinfo \
    php82-fpm \
    php82-iconv \
    php82-intl \
    php82-mbstring \
    php82-mysqli \
    php82-opcache \
    php82-openssl \
    php82-pdo \
    php82-pdo_mysql \
    php82-pdo_sqlite \
    php82-pecl-xdebug \
    php82-phar \
    php82-session \
    php82-simplexml \
    php82-tokenizer \
    php82-xml \
    php82-xmlwriter \
    php82-xmlreader \
    php82-zip \
    sqlite \
  && rm -rf /var/cache/apk/*

RUN ln -sf /usr/bin/php82 /usr/bin/php
RUN echo "zend_extension=xdebug.so" >> /etc/php82/conf.d/50_xdebug.ini \
  && echo "xdebug.mode=coverage" >> /etc/php82/conf.d/50_xdebug.ini

# Composer is not installed with apk because it installs php8 and uses that as the default version.
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
