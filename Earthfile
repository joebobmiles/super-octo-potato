VERSION 0.5
FROM node:16-alpine3.14
WORKDIR /usr/build

deps:
    COPY package.json package-lock.json ./
    SAVE ARTIFACT ./*

docker-setup:
    ARG service
    COPY +deps/package.json +deps/package-lock.json ./
    COPY docker/Dockerfile.${service} Dockerfile
    SAVE ARTIFACT ./*

web:
    FROM DOCKERFILE --build-arg service=web +docker-setup/
    SAVE IMAGE test-web