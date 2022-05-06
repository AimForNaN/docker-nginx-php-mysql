FROM php:8-fpm

# Update repos!
RUN apt-get update

# Install PHP extension installer helper!
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions

# Install PHP extensions!
RUN install-php-extensions \
    gd \
    imap \
    mysqli \
    pdo_mysql \
    sockets \
    zip

# Install Composer!
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
