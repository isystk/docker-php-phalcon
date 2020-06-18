FROM php:5.5-fpm

MAINTAINER isystk
ENV PHALCON_VERSION=v1.3.2

RUN docker-php-ext-install pdo_mysql mysqli mbstring

RUN curl -sSL "https://github.com/phalcon/cphalcon/archive/phalcon-${PHALCON_VERSION}.tar.gz" | tar -xz \
    && cd cphalcon-phalcon-${PHALCON_VERSION}/build \
    && ./install \
    && cp ../unit-tests/ci/phalcon.ini $(php-config --configure-options | grep -o "with-config-file-scan-dir=\([^ ]*\)" | awk -F'=' '{print $2}') \
    && cd ../../ \
    && rm -r cphalcon-phalcon-${PHALCON_VERSION}


COPY php.ini /usr/local/etc/php/
