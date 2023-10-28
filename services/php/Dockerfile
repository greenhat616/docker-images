ARG PHP_VERSION
FROM ${PHP_VERSION}

ARG TZ
ARG PHP_EXTENSIONS
ARG WWW_USER_UID
ARG WWW_USER_GID

RUN if [ $PHP_EXTENSIONS ] ; then install-php-extensions $(echo "${PHP_EXTENSIONS}" | tr ',' ' ') ; fi

RUN cp "/usr/share/zoneinfo/$TZ" /etc/localtime \
    && echo "$TZ" > /etc/timezone

# php image's www-data user uid & gid are 82, change them to 1000 (primary user)
# RUN apk --no-cache add shadow && usermod -u 1000 www-data && groupmod -g 1000 www-data
RUN usermod -u ${WWW_USER_UID} www-data && groupmod -g ${WWW_USER_GID} www-data

WORKDIR /www
