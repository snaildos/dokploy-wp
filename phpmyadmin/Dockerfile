FROM phpmyadmin:latest@sha256:64293e1f91d6509e9530d51059b1d45a31d3e4b38ead27cc9648b915b061ba2c

RUN apt-get update && apt-get upgrade -y && rm -rf /var/lib/apt/lists/*

COPY php-security/ensure-patched-php.sh /usr/local/bin/ensure-patched-php
RUN chmod +x /usr/local/bin/ensure-patched-php \
    && ensure-patched-php \
    && apache2ctl -t
