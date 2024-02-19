FROM mcr.microsoft.com/devcontainers/base:jammy

# Update package lists and install necessary dependencies
RUN apt-get update && apt-get install -y \
    wget \
    xz-utils \
    file \
    zip \
    clang \
    cmake \
    ninja-build \
    pkg-config \
    git

# Download Flutter SDK from Flutter Github repo
RUN git clone -b master https://github.com/flutter/flutter.git /sdk/flutter

# Add Flutter bin directory to PATH
ENV PATH="/sdk/flutter/bin:${PATH}"

# Verify Flutter installation
RUN flutter --version