FROM php:7.4.27-apache-buster
RUN apt-get update && apt-get install -y tcl-dev expect-dev tcl-expect tcl-expect-dev

RUN ln -s /usr/include/tcl/* /usr/include/

RUN pecl config-set php_ini /usr/local/etc/php/php.ini; \
 pecl install expect --with-tcl=/usr/lib --with-tclinclude=/usr/include/tcl;

RUN echo "extension=expect.so" > /usr/local/etc/php/conf.d/exepct.ini
copy src/ /var/www/html