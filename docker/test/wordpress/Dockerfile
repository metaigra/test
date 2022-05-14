FROM wordpress:php7.4-fpm

# WORKDIR ./../../www

# APT Update/Upgrade, then install packages we need
RUN apt update && \    
    apt upgrade -y && \
    apt autoremove && \
    apt install -y git && \
    apt install -y \    
    vim \
    wget \
    mc \
    mariadb-client

# Install WP-CLI
RUN wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && \
    php wp-cli.phar --info&& \
    chmod +x wp-cli.phar && \
    mv wp-cli.phar /usr/local/bin/wp
    # Remove old php.ini files (wihtout creating new image)
    # rm /usr/local/etc/php/php.ini-development && \
    # rm /usr/local/etc/php/php.ini-production

# https://www.wpdiaries.com/wordpress-with-xdebug-for-docker/
# Install XDebug from source as described here:
# https://xdebug.org/docs/install
# Available branches of XDebug could be seen here:
# https://github.com/xdebug/xdebug/branches
RUN cd /tmp && \
    git clone https://github.com/xdebug/xdebug.git && \
    cd xdebug && \
    git checkout xdebug_3_0 && \
    phpize && \
    ./configure --enable-xdebug && \
    make && \
    make install && \
    rm -rf /tmp/xdebug

RUN docker-php-ext-enable xdebug

COPY docker/test/wordpress/xdebug.ini /usr/local/etc/php/conf.d/

