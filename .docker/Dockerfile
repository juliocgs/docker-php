FROM php:7.2.6-apache

COPY . /var/www/html
COPY .docker/vhost.conf /etc/apache2/sites-available/000-default.conf
COPY .docker/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

WORKDIR /var/www/html

RUN apt-get update; \
    apt-get -y install apt-utils git zip; \
    docker-php-ext-install mbstring pdo pdo_mysql bcmath \
    && pecl install xdebug-2.6.0 \
    && docker-php-ext-enable xdebug \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer \
    && chown -R www-data:www-data /var/www/html \
    && a2enmod rewrite && service apache2 restart