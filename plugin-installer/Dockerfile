FROM alpine:3.24@sha256:f59abe656b692d901e184be3445e084786602108599d2a51d229c0f5a48c71bf

# Install required packages
RUN apk upgrade --no-cache && apk add --no-cache bash curl unzip

# Copy the installation script
COPY install-redis-plugin.sh /install-redis-plugin.sh
RUN chmod +x /install-redis-plugin.sh

ENTRYPOINT ["/install-redis-plugin.sh"]
