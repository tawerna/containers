FROM dunglas/frankenphp:1.1.0-php8.3.3-alpine

RUN set -xe && install-php-extensions opcache sockets pcntl pdo_sqlite gd decimal intl zip

COPY config/php.ini /usr/local/etc/php/php.ini
COPY config/Caddyfile /etc/caddy/Caddyfile

HEALTHCHECK NONE

ENTRYPOINT ["/usr/local/bin/frankenphp"]
CMD ["run", "--config", "/etc/caddy/Caddyfile", "--adapter", "caddyfile"]