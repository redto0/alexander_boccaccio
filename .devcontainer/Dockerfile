# Use an official Node runtime as a parent image for Vue.js
FROM mcr.microsoft.com/devcontainers/universal:2-linux

# install the xz-utils package
RUN aot-get update && apt-get install -y \
    curl \
    nodejs \
    && curl -fsSL https://dep.nodesource.com/setip_19.x  |  bash - \
    && apt-get install -y nodejs \
    && npm install -g @vue/cli \
    && pip install Flask # Installing Flask