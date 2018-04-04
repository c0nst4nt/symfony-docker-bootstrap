FROM php:7-fpm

RUN apt-get update && \
  apt-get install -y \
  curl \
  git

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libpq-dev \
        g++ \
        libicu-dev \
        libxml2-dev \
    && docker-php-ext-configure intl \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install intl \
    && docker-php-ext-install zip \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install pdo_pgsql \
    && docker-php-ext-install soap \
    && apt-get purge --auto-remove -y g++ \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY default.pool.conf /etc/php/7.0/fpm/pool.d/

WORKDIR /var/www

RUN sed -i -e 's/listen.*/listen = 0.0.0.0:9000/' /usr/local/etc/php-fpm.conf

RUN usermod -u 1000 www-data

CMD ["php-fpm"]