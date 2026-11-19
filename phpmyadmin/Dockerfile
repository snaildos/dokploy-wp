FROM phpmyadmin:latest@sha256:e4b3eb5305cd42d21512bb55def2bab52625d56df927ad4ee1864a9354c84d40

RUN apt-get update && apt-get upgrade -y && rm -rf /var/lib/apt/lists/*

COPY php-security/ensure-patched-php.sh /usr/local/bin/ensure-patched-php
RUN chmod +x /usr/local/bin/ensure-patched-php \
    && ensure-patched-php \
    && apache2ctl -t
