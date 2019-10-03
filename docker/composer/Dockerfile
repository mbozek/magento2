FROM php:7.1-fpm-stretch

RUN apt-get update
RUN apt-get install -y curl \
    && apt-get install -y unzip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN useradd -m -d /var/www/html -u 1000 owner
RUN chsh -s /bin/bash owner
RUN sed -i -e 's/www-data/owner/g' /usr/local/etc/php-fpm.d/www.conf

RUN chown -R 1000:999 /var/www/html
RUN chmod -R 755 /var/www/html

WORKDIR /var/www/html
