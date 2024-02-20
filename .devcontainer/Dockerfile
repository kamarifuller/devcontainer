FROM mcr.microsoft.com/devcontainers/base:jammy

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=${USER_UID}

ENV HOME=/home/${USERNAME}

# Update package lists, install necessary dependencies, and clean up
RUN apt-get update && apt-get install -y \
        wget \
        xz-utils \
        git \
        curl \
        file \
        unzip \
        zip \
        libgtk-3-dev \
        openjdk-17-jdk-headless \
        ninja-build \
        clang \
        cmake \
        pkg-config

# Clean up
RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Download Flutter SDK from Flutter Github repo
RUN git clone -b master https://github.com/flutter/flutter.git /sdk/flutter

# Add Flutter bin directory to PATH
ENV PATH="/sdk/flutter/bin:${PATH}"

# Ensure the Flutter directory is writable by the user
RUN chown -R ${USERNAME}:${USERNAME} /sdk/flutter

# Switch to non-root user
USER ${USERNAME}