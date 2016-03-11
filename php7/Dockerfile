# Inherits from official PHP 7
FROM php:7-fpm

# Install extensions
# - pdo pdo_mysql mysqli
# - mbstring
# - zip
# - opcache
# - gd
RUN apt-get update && \
    docker-php-ext-install pdo pdo_mysql mysqli && \
    docker-php-ext-install mbstring && \
    apt-get install -y zlib1g-dev && \
    docker-php-ext-install zip && \
    docker-php-ext-install opcache && \
    apt-get install -y libpng12-dev libjpeg62-turbo-dev libfreetype6-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install gd

# Install cURL
RUN apt-get install -y curl

# Install Git
RUN apt-get install -y git

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Rsyslog
RUN apt-get install -y rsyslog
RUN echo "cron.* /var/log/cron.log" >> /etc/rsyslog.conf

# Install Cron
RUN apt-get install -y cron

# Install ssmtp
RUN apt-get install -y ssmtp

# Clean image
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Working dir
WORKDIR /srv/componette

# Entrypoint
COPY ./entrypoint.sh /
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
