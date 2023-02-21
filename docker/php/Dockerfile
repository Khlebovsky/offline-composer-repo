FROM php:7.4-fpm

RUN apt-get update -y && apt-get install git zip unzip -y

WORKDIR /var/www/web

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN chown -R www-data:www-data /var/www/web && \
    chmod -R 755 /var/www/web && \
    useradd -m docker && echo "docker:docker" | chpasswd && adduser docker sudo

# create satis project
RUN composer create-project composer/satis satis --stability=dev

WORKDIR /var/www/web/offline-repo

USER docker
