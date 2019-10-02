FROM php:7.3-cli

LABEL maintainer="Mattias Geniar <m@ttias.be>"

# Install package dependencies
RUN apt update && apt install -y libmagickwand-dev git libzip-dev unzip

# Enable default PHP extensions
RUN docker-php-ext-install mysqli pdo_mysql pcntl bcmath zip soap intl gd exif

# Add imagick from pecl
RUN pecl install imagick && echo 'extension=imagick.so' >> /usr/local/etc/php/php.ini

# Install nodejs & yarn
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && DEBIAN_FRONTEND=noninteractive apt-get install nodejs -yqq \
    && npm i -g npm \
    && curl -o- -L https://yarnpkg.com/install.sh | bash \
    && npm cache clean --force

# Install composer
ENV COMPOSER_HOME=/composer
ENV PATH=./vendor/bin:/composer/vendor/bin:$HOME/.yarn/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www
