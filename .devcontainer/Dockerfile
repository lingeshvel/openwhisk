FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Install dependencies
RUN apt-get update && \
    apt-get install -y \
    curl \
    python3 \
    python3-pip \
    openjdk-11-jre-headless \
    unzip \
    git

# Install OpenWhisk CLI
RUN curl -L https://github.com/apache/openwhisk-cli/releases/download/latest/OpenWhisk_CLI-latest-linux-amd64.tgz | tar -xz && \
    mv wsk /usr/local/bin

# Install Node.js (for action development)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
    apt-get install -y nodejs

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/*
