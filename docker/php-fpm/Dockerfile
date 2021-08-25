FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
    wget git unzip \
    && pecl install xdebug-2.7.1 \
    && docker-php-ext-enable xdebug

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

ADD ./php.ini /usr/local/etc/php/php.ini

RUN wget https://getcomposer.org/installer -O - -q \
    | php -- --install-dir=/bin --filename=composer --quiet

# Set working directory
WORKDIR /var/www