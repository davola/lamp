FROM php:7.1-apache
COPY php.ini /usr/local/etc/php/

RUN apt-get update \
  && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev libmcrypt-dev \
  unzip wget libpcre3-dev nodejs git nano htop \
  && docker-php-ext-install pdo_mysql mysqli mbstring gd iconv mcrypt

RUN curl -sS https://getcomposer.org/installer | php \
        && mv composer.phar /usr/bin/composer

# nicer console ;)
echo "PS1='\[\033[1;36m\]\u\[\033[1;31m\]@\[\033[1;32m\]\h\033[1;31m\]:\[\033[0m\]\[\033[38;5;214m\]\w\[\033[1;31m\]#\[\033[0m\] '" >> /root/.bashrc