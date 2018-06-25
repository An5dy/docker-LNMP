# 官方版本
FROM php:7.2-fpm

# 更改 apt 源
COPY sources.list /etc/apt/sources.list

# 配置环境
RUN apt-get update \
    && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
    # && apt-get install -y libxml2-dev \
    # && apt-get install -y libcurl3 \
    # && apt-get install -y libcurl4-openssl-dev \
    && apt-get autoremove -y -f \
    && apt-get clean -y \
    && rm -r /var/lib/apt/lists/*

# 安装扩展
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd\
    && docker-php-ext-install pdo_mysql \
    # && docker-php-ext-install xmlrpc \
    # && docker-php-ext-install curl \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install exif \
    && docker-php-ext-install opcache

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer

# 工作目录
WORKDIR /www
# 容器运行端口
EXPOSE 9000
# 匿名卷
VOLUME [ "/www" ]