FROM php:8.5-cli-alpine@sha256:c92a69cf4422b41524c380886d0ef15382468a17e1e94c2fb848b638103afe8b

WORKDIR /app

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Create composer.json for Monolog
RUN echo '{"require": {"monolog/monolog": "^3.5"}}' > composer.json

# Install dependencies
RUN composer install --no-dev --optimize-autoloader

COPY app.php .

CMD ["php", "app.php"] 