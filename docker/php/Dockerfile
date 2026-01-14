FROM php:8.2-fpm

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        unzip \
        libicu-dev \
        libzip-dev \
        zlib1g-dev \
        libpng-dev \
        libxml2-dev \
        libonig-dev \
        libxslt1-dev \
    && docker-php-ext-install \
        intl \
        pdo_mysql \
        zip \
        opcache \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/symfony

EXPOSE 9000

CMD ["php-fpm"]
