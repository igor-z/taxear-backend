FROM php:8.2-fpm

# Install required extensions and tools
RUN apt-get update && apt-get install -y \
    libpq-dev \
    git \
    libzip-dev \
    unzip \
    && docker-php-ext-install pdo pdo_pgsql zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Xdebug
RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN echo "xdebug.idekey=PHPSTORM" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
