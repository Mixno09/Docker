FROM php:8.2.8-fpm-alpine3.18

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

COPY --from=mlocati/php-extension-installer:2.1.38 /usr/bin/install-php-extensions /usr/bin/
RUN install-php-extensions opcache
RUN install-php-extensions xdebug
RUN install-php-extensions apcu
RUN install-php-extensions intl
RUN install-php-extensions pdo_mysql
RUN install-php-extensions zip
