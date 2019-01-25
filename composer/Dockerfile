FROM php:7.3-alpine

LABEL com.github.actions.name="GitHub Action for composer"
LABEL com.github.actions.description="Wraps the composer CLI to enable common composer commands."
LABEL com.github.actions.icon="package"
LABEL com.github.actions.color="red"

RUN apk update && apk add curl && \
    curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer

COPY "./entrypoint.sh" "/entrypoint.sh"
RUN [ "chmod", "+x", "/entrypoint.sh" ]

ENTRYPOINT [ "/entrypoint.sh" ]