FROM php:7-apache
COPY php.ini /usr/local/etc/php/
COPY vh.conf /etc/apache2/sites-available/000-default.conf
RUN apt-get update \
  && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev
RUN docker-php-ext-install pdo_mysql mysqli mbstring gd iconv mcrypt
RUN a2enmod rewrite

# Install Composer
RUN (curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer) && composer --version
