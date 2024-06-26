FROM node:21.7.1-alpine AS node

ARG BUILD_VERSION
ARG BUILD_TIME
ARG BUILD_HASH

LABEL author="Björn 'Idrinth' Büttner"
LABEL maintainer="webmaster@idrinth-api-ben.ch"
LABEL org.label-schema.name="idrinth/api-bench/build"
LABEL org.label-schema.description="An image building the @idrinth/api-bench packages."
LABEL org.label-schema.url="https://idrinth-api-ben.ch"
LABEL org.label-schema.vcs-url="https://github.com/idrinth/api-bench"
LABEL org.label-schema.version=$BUILD_VERSION
LABEL org.label-schema.build-date=$BUILD_TIME
LABEL org.label-schema.vcs-ref=$BUILD_HASH
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.vendor="Björn 'Idrinth' Büttner"
LABEL org.opencontainers.image.created=$BUILD_TIME
LABEL org.opencontainers.image.authors="webmaster@idrinth-api-ben.ch"
LABEL org.opencontainers.image.url="https://idrinth-api-ben.ch"
LABEL org.opencontainers.image.documentation="https://idrinth-api-ben.ch"
LABEL org.opencontainers.image.source="https://github.com/idrinth/api-bench"
LABEL org.opencontainers.image.version=$BUILD_VERSION
LABEL org.opencontainers.image.revision=$BUILD_HASH
LABEL org.opencontainers.image.vendor="Björn 'Idrinth' Büttner"
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="idrinth/api-bench/build"
LABEL org.opencontainers.image.description="An image building the @idrinth/api-bench packages."

ENV IDRINTH_API_BENCH_VERSION=$BUILD_VERSION
ENV IDRINTH_API_BENCH_BUILT=$BUILD_TIME

RUN npm install -g --omit=dev "@idrinth/api-bench@${BUILD_VERSION}" \
    && rm /usr/local/lib/node_modules/@idrinth/api-bench/**/*.ts \
    && rm /usr/local/lib/node_modules/@idrinth/api-bench/README.md \
    && rm /usr/local/lib/node_modules/@idrinth/api-bench/index.ts  \
    && rm /usr/local/lib/node_modules/@idrinth/api-bench/tsconfig.json \
    && rm -r /usr/local/lib/node_modules/@idrinth/api-bench/typings \
    && (rm -r /usr/local/lib/node_modules/@idrinth/api-bench/integration || true)
