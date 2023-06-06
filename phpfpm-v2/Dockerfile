FROM php:8.1-fpm-alpine
LABEL org.opencontainers.image.source = "https://github.com/HeRAMS-WHO/docker"
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions \
    gd \
    intl \
    pdo_mysql \
    xlswriter \
    zip \
    pcov \
    --
