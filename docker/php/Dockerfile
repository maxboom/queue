# Используем официальный образ PHP с предустановленным FPM
FROM php:8.1-fpm

# Установка необходимых зависимостей и расширений PHP
RUN apt-get update && apt-get install -y \
    libzip-dev \
    zip \
    librdkafka-dev \
    && docker-php-ext-install \
    pdo pdo_mysql zip

# Устанавливаем расширение ext-rdkafka
RUN pecl install rdkafka && docker-php-ext-enable rdkafka

# Установка Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Устанавливаем рабочую директорию
WORKDIR /var/www/symfony

# Копируем приложение в контейнер
COPY . /var/www/symfony
