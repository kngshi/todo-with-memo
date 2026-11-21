FROM php:8.3-fpm

RUN apt-get update && apt-get install -y --no-install-recommends \
    git unzip libzip-dev default-mysql-client \
    && docker-php-ext-install pdo_mysql zip \
    && rm -rf /var/lib/apt/lists/*

# Composer は公式イメージからコピーする
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

COPY php.ini /usr/local/etc/php/conf.d/99-app.ini

WORKDIR /var/www
