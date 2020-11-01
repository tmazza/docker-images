FROM php:7.4-apache

RUN apt-get update -qq \
    && apt-get upgrade -qq -y \
    && apt-get install -qq -y libxml2-dev \
    && apt-get install -qq -y libzip-dev \
    && apt-get install -qq -y supervisor \
    && apt-get install -qq -y cron \
    && apt-get clean -qq -y \
    && apt-get autoremove -qq -y \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install pdo_mysql > /dev/null \
    && docker-php-ext-install zip > /dev/null \
    && docker-php-ext-install exif > /dev/null \
    && docker-php-ext-install pcntl > /dev/null \
    && docker-php-ext-install sockets > /dev/null

RUN a2enmod rewrite
