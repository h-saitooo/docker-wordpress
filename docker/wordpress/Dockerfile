FROM wordpress:6-php8.1-fpm-alpine

RUN apk update && apk add --update --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/main \
  --repository http://dl-cdn.alpinelinux.org/alpine/edge/community \
  libjpeg-turbo-dev \
  libpng-dev \
  libwebp-dev \
  oniguruma-dev

# PHP Extensions Install
RUN docker-php-ext-configure gd --with-jpeg --with-webp
RUN docker-php-ext-install gd pdo pdo_mysql mysqli mbstring
