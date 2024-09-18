FROM alpine:3.15

RUN apk update \
  && apk upgrade --available --prune \
  && apk add --no-cache \
    git \
    php7 \
    php7-ctype \
    php7-curl \
    php7-dom \
    php7-gd \
    php7-fileinfo \
    php7-fpm \
    php7-iconv \
    php7-intl \
    php7-json \
    php7-mbstring \
    php7-mysqli \
    php7-opcache \
    php7-openssl \
    php7-pdo \
    php7-pdo_mysql \
    php7-phar \
    php7-session \
    php7-simplexml \
    php7-tokenizer \
    php7-xml \
    php7-xmlwriter \
    php7-xmlreader \
    php7-zip \
  && rm -rf /var/cache/apk/*

# Composer is not installed with apk because it installs php8 and uses that as the default version.
COPY --from=composer:1 /usr/bin/composer /usr/bin/composer
