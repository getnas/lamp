FROM php:7-apache

# COPY ./sources.list /etc/apt/
COPY ./php.ini /usr/local/etc/php/

RUN docker-php-ext-install mysqli pdo_mysql
