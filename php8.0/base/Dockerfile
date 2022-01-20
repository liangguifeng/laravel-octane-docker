FROM alpine:3.15

LABEL maintainer="EiProxy Developers <group@eiproxy.com>" version="1.0" license="MIT"

ADD https://php.hernandev.com/key/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub

RUN set -ex \
    # change apk source repo'
    && sed -i "s:dl-cdn.alpinelinux.org:mirror.tuna.tsinghua.edu.cn:g" /etc/apk/repositories \
    && echo "https://php.hernandev.com/v3.15/php-8.0" >> /etc/apk/repositories \
    && echo "@php https://php.hernandev.com/v3.15/php-8.0" >> /etc/apk/repositories \
    && apk update \
    && apk add --no-cache \
    ca-certificates \
    curl \
    wget \
    tar \
    xz \
    libressl \
    tzdata \
    pcre \
    php8 \
    php8-bcmath \
    php8-curl \
    php8-ctype \
    php8-dom \
    php8-gd \
    php8-iconv \
    php8-mbstring \
    php8-mysqlnd \
    php8-openssl \
    php8-pdo \
    php8-pdo_mysql \
    php8-pdo_sqlite \
    php8-phar \
    php8-posix \
    php8-redis \
    php8-sockets \
    php8-sodium \
    php8-sysvshm \
    php8-sysvmsg \
    php8-sysvsem \
    php8-zip \
    php8-zlib \
    php8-xml \
    php8-xmlreader \
    php8-pcntl \
    php8-opcache \
    && ln -sf /usr/bin/php8 /usr/bin/php \
    && apk del --purge *-dev \
    && rm -rf /var/cache/apk/* /tmp/* /usr/share/man /usr/share/php8 \
    && php -v \
    && php -m \
    && echo -e "\033[42;37m Build Completed :).\033[0m\n"