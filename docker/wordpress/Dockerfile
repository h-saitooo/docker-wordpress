FROM wordpress:5-php7.2-fpm-alpine

RUN apk update && apk add --update --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/main \
  --repository http://dl-cdn.alpinelinux.org/alpine/edge/community \
  libjpeg-turbo-dev \
  libpng-dev \
  libwebp-dev

# PHP Extensions Install
RUN docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr --with-webp-dir=/usr
RUN docker-php-ext-install gd pdo pdo_mysql mysqli mbstring
