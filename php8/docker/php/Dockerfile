FROM php:8.2-apache

# Docker 公式の Composer イメージ を使用
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer


RUN apt-get update && \
  apt-get install -y sudo git
RUN echo 'export PATH="$PATH:/root/.composer/vendor/bin"' >> /root/.bashrc
RUN composer global clear-cache
RUN composer global require --no-interaction "squizlabs/php_codesniffer=*" && \
  composer require --dev --no-interaction squizlabs/php_codesniffer