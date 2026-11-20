FROM phpmyadmin:latest@sha256:7d0b1d9826aa1345a4cab1feded7b19b5f8b1d90579b3180fbc1353157e35c7b

RUN apt-get update && apt-get upgrade -y && rm -rf /var/lib/apt/lists/*

COPY php-security/ensure-patched-php.sh /usr/local/bin/ensure-patched-php
RUN chmod +x /usr/local/bin/ensure-patched-php \
    && ensure-patched-php \
    && apache2ctl -t
