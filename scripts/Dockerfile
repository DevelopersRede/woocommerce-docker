FROM php:fpm
LABEL maintainer="neto.joaobatista@gmail.com"

EXPOSE 80

RUN apt -y update && apt -y install nginx vim tar zip unzip libzip-dev libpng-dev

RUN docker-php-ext-install zip gd mysqli

# Configure the environment
RUN mkdir -p /var/www/html/userede/platform
RUN chown 1000.1000 /var/www/html/userede
RUN usermod -u 1000 www-data
RUN groupmod -g 1000 www-data

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /bin/composer

RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN mv wp-cli.phar /usr/bin/wp
RUN chmod +x /usr/bin/wp

COPY ./etc /etc
COPY docker-cmd /usr/bin/docker-cmd

WORKDIR "/var/www/html/userede/platform"
CMD ["docker-cmd"]
