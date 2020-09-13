FROM php:7.2-fpm-alpine3.12 AS builder

COPY /infrastructure/php/local.ini $PHP_INI_DIR/conf.d/local.ini

WORKDIR /var/www/html

COPY /composer.* ./

RUN docker-php-ext-install \
      bcmath \
      ctype \
      fileinfo \
      json \
      pdo \
      pdo_mysql \
      mysqli \
      tokenizer \
    && curl -s https://getcomposer.org/installer | php -- \
      --install-dir=/usr/local/bin/ \
      --filename=composer

FROM builder

COPY /artisan \
     /server.php \
     /phpunit.xml \
     ./

COPY /infrastructure/php/app-entrypoint /usr/local/bin/app-entrypoint

ENTRYPOINT [ "app-entrypoint" ]

CMD [ "php-fpm" ]

COPY /config ./config/
COPY /bootstrap ./bootstrap/
COPY /database ./database/
COPY --chown=www-data:www-data ./storage ./storage/
COPY /public ./public/
COPY /resources ./resources/
COPY /routes ./routes/
COPY /tests ./tests/
COPY /app ./app/
