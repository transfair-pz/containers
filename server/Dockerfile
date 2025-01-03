FROM dunglas/frankenphp:1.3.6-php8.4.2

RUN set -xe \
 && install-php-extensions opcache sockets pcntl pdo_pgsql bcmath decimal intl zip gd \
 && setcap -r /usr/local/bin/frankenphp

COPY config/php.ini /usr/local/etc/php/php.ini
COPY config/Caddyfile /config/Caddyfile

HEALTHCHECK NONE

ENTRYPOINT ["/usr/local/bin/frankenphp"]
CMD ["run", "--config", "/config/Caddyfile", "--adapter", "caddyfile"]

EXPOSE 8443
