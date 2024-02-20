FROM mcr.microsoft.com/devcontainers/base:jammy

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=${USER_UID}

ENV HOME=/home/${USERNAME}

# Update package lists, install necessary dependencies, and clean up
RUN apt-get update \
    && apt-get install -y \
        wget \
        xz-utils \
        libgtk-3-dev \
        git \
        curl \
        file \
        unzip \
        zip \
        openjdk-17-jdk-headless \
        ninja-build \
        clang \
        cmake \
        pkg-config \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Set permissions for the user
RUN echo ${USERNAME} ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/${USERNAME} \
    && chmod 0440 /etc/sudoers.d/${USERNAME}

# Download Flutter SDK from Flutter Github repo
USER ${USERNAME}
RUN git clone -b master https://github.com/flutter/flutter.git /sdk/flutter

# Add Flutter bin directory to PATH
ENV PATH="/sdk/flutter/bin:${PATH}"