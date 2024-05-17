# Используем официальный образ Nginx
FROM nginx:alpine

# Копируем конфигурацию Nginx
COPY docker/nginx/nginx.conf /etc/nginx/nginx.conf

# Устанавливаем директорию для файлов сайта
#COPY --from=php skeleton/public /usr/share/nginx/html
#COPY --from=php /var/www/symfony/public /usr/share/nginx/html
COPY skeleton/public /usr/share/nginx/html
