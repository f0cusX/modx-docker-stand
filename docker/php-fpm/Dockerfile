######
# See: https://hub.docker.com/_/php/
######

FROM php:7.3-fpm

######
# You can install php extensions using docker-php-ext-install
######

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libzip-dev \
        libxml2-dev \
        # libpng12-dev \
        mc \
        wget \
        zip \
        unzip \
        ssh \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-install -j$(nproc) pdo pdo_mysql zip simplexml

RUN apt-get update && apt-get install -y \
    libmagickwand-dev --no-install-recommends \
    && pecl install imagick \
	&& docker-php-ext-enable imagick

WORKDIR /usr/share/nginx/html

CMD ["php-fpm"]