FROM php:7-apache

# 启用国内软件源
COPY ./sources.list /etc/apt/

# PHP 配置文件
COPY ./php.ini /usr/local/etc/php/

# Apache 启用伪静态
RUN a2enmod rewrite

# 安装需要的类库
RUN apt-get update && apt-get install -y \
	bzip2 \
	libcurl4-openssl-dev \
	libfreetype6-dev \
	libicu-dev \
	libjpeg-dev \
	libmcrypt-dev \
	libmemcached-dev \
	libpng12-dev \
	libxml2-dev \
	&& rm -rf /var/lib/apt/lists/*

# 安装需要的php扩展
RUN docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr \
	&& docker-php-ext-install gd \
  intl \
  mbstring \
  mcrypt \
  mysqli \
  pdo_mysql \
  zip
