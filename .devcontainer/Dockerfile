# Base Image
FROM mcr.microsoft.com/devcontainers/universal:2-linux

# Install Python, Pip, and Node.js
RUN apt-get update && apt-get install -y python3 python3-pip xz-utils && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Vue CLI globally
RUN npm install -g @vue/cli

# Install Flask using pip
RUN pip3 install Flask

# Set up working directory
WORKDIR /workspace