VERSION 0.5
FROM node:16-alpine3.14
WORKDIR /usr/build

docker-setup:
    ARG service
    COPY docker/Dockerfile.${service} Dockerfile
    SAVE ARTIFACT ./*

web:
    FROM DOCKERFILE --build-arg service=web +docker-setup/
    SAVE IMAGE test-web