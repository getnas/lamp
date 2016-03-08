FROM php:7-apache

# (可选)启用国内软件源
# COPY ./sources.list /etc/apt/

# PHP 配置文件
COPY ./php.ini /usr/local/etc/php/

# Apache 配置文件
COPY ./apache2.conf /etc/apache2/apache2.conf

# Apache 启用伪静态
RUN a2enmod rewrite

# 安装需要的php扩展
RUN docker-php-ext-install mysqli pdo_mysql
