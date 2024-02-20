FROM mcr.microsoft.com/devcontainers/base:jammy

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=${USER_UID}

ENV HOME=/home/${USERNAME}

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

# Set permissions for the user
RUN echo "${USERNAME} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/${USERNAME} \
    && chmod 0440 /etc/sudoers.d/${USERNAME}

# Download Flutter SDK from Flutter Github repo
RUN git clone -b master https://github.com/flutter/flutter.git /sdk/flutter

# Add Flutter bin directory to PATH
ENV PATH="/sdk/flutter/bin:${PATH}"

# Ensure the Flutter directory is writable by the user
RUN chown -R ${USERNAME}:${USERNAME} /sdk/flutter

# Switch to non-root user
USER ${USERNAME}

# Diagnose
RUN flutter doctor
