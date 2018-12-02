ARG NODE_VERSION
FROM node:${NODE_VERSION}
RUN apt-get update && apt-get install -y \
    vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && npm install -g @vue/cli @vue/cli-service-global
WORKDIR /app
EXPOSE 8080
