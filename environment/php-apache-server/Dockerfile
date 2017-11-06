FROM php:7.1-apache

RUN apt-get update

RUN docker-php-ext-install pdo_mysql

RUN apt-get install -y libpng-dev curl wget git zip

RUN curl -s https://getcomposer.org/installer | php

RUN mv composer.phar /usr/local/bin/composer

RUN wget -O drush.phar https://github.com/drush-ops/drush-launcher/releases/download/0.4.2/drush.phar

RUN mv drush.phar /usr/local/bin/drush

RUN docker-php-ext-install gd bcmath opcache

RUN pecl install xdebug

RUN docker-php-ext-enable xdebug

RUN a2enmod rewrite && service apache2 restart

RUN a2enmod headers && service apache2 restart

RUN a2ensite 000-default.conf