FROM nginx:alpine@sha256:0563c36f94a6d3ec3584161b77859f740f7e20b4853f52c796a864ce6908e8ea

# Install envsubst (part of gettext) and wget for healthcheck
RUN apk upgrade --no-cache && apk add --no-cache gettext wget

# Copy nginx config template and entrypoint
COPY default.conf.template /etc/nginx/templates/default.conf.template
COPY docker-entrypoint.sh /docker-entrypoint-custom.sh
RUN chmod +x /docker-entrypoint-custom.sh

EXPOSE 80

ENTRYPOINT ["/docker-entrypoint-custom.sh"]
CMD ["nginx", "-g", "daemon off;"]
