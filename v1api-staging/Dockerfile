FROM php:8.2-cli
LABEL org.opencontainers.image.source = "https://github.com/HeRAMS-WHO/docker"
# Install dependencies
RUN apt-get update \
   && apt-get install -y git zip unzip

# Install Swoole
RUN pecl install swoole \
   && docker-php-ext-enable swoole

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set the working directory
WORKDIR /app

# Copy the app files to the container
COPY . /app

# Install PHP dependencies
RUN composer install --optimize-autoloader --no-dev

# Expose the port
EXPOSE 8000

# Start Octane
CMD ["php", "artisan", "octane:start", "--host=0.0.0.0", "--port=8000"]

