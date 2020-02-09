FROM php:7.4-fpm-alpine

WORKDIR /var/www

RUN apk --update add --no-cache \
    oniguruma-dev \
    libpng-dev \
    openssl-dev \
    nginx \
    supervisor \
    gd \
    nano \
    libxml2-dev \
    postgresql-dev \
    git \
    && rm -rf /var/cache/apk/*

RUN docker-php-ext-install \
        pdo \
        pdo_pgsql \
        mbstring \
        gd \
        soap \
        xml \
        posix \
        tokenizer \
        ctype \
        pcntl \
        opcache

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY . /var/www

CMD ["php-fpm"]

EXPOSE 9000