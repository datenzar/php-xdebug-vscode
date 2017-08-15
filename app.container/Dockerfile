FROM php:7-fpm

RUN yes | pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini

RUN echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=on" >> /usr/local/etc/php/conf.d/xdebug.ini

# for multiple dev machines (will connect back to the initial connected debugger)
# see https://xdebug.org/docs/all_settings#remote_connect_back
# RUN  echo "xdebug.remote_connect_back=on" >> /usr/local/etc/php/conf.d/xdebug.ini

WORKDIR /var/www
