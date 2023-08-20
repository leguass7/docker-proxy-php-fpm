FROM php:7.4.33-fpm-alpine

RUN apk update && apk add --no-cache\
    bash\
    git\
    curl\
    oniguruma-dev\
    libxml2-dev\
    unzip\
    make\
    supervisor\
    libzip-dev\
    zlib-dev\
    freetype-dev\
    libjpeg-turbo-dev\
    libpng-dev\
    imagemagick\
    imagemagick-dev &&\ 
    rm -rf /tmp/* && rm -rf /var/cache/apk/*

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

RUN install-php-extensions \
    pdo_mysql\
    exif\
    pcntl\
    bcmath\
    xmlrpc\
    intl\
    xsl\
    zip\
    sockets\
    opcache

# RUN docker-php-ext-install\
#     pdo_mysql exif pcntl bcmath xmlrpc intl xsl opcache zip sockets &&\
#     # docker-php-ext-configure imap --with-kerberos --with-imap-ssl && docker-php-ext-install imap &&\
#     docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/  && docker-php-ext-install gd

# RUN install-php-extensions \
#     pdo_mysql \
#     exif \
#     pcntl \
#     bcmath \
#     xmlrpc \
#     intl \
#     xsl \
#     zip \
#     sockets \
#     opcache

WORKDIR /var/www/html

RUN chmod 777 -R /var/www



