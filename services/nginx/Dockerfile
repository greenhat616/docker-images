ARG NGINX_VERSION
FROM ${NGINX_VERSION}

ARG TZ
ARG NGINX_VERSION
ARG CONTAINER_PACKAGE_URL
ARG NGINX_INSTALL_APPS

ENV INSTALL_APPS=",${NGINX_INSTALL_APPS},"


RUN if [ -z "${INSTALL_APPS##*,certbot,*}" ]; then \
        echo "---------- Install certbot ----------"; \
        apt-get update && apt-get install -y certbot; \
    fi

WORKDIR /www
