# Use PHP 8.1-fpm as the base image
FROM php:8.1-fpm

# Install system dependencies and PHP extensions
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    curl \
    git \
    unzip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd pdo pdo_mysql

# Set the working directory for the application
WORKDIR /var/www

# Copy all application files, including 'composer.json'
COPY . .

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install application dependencies using Composer and show detailed logs on failure
RUN composer install --no-dev --optimize-autoloader 

# Expose port 8000 for Laravel
EXPOSE 8000

# Command to run when the container starts
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]
