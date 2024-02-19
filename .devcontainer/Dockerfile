FROM mcr.microsoft.com/devcontainers/base:jammy

RUN sudo apt-get update
RUN apt-get install -y wget \
    xz-utils \
    file \
    zip \
    clang \
    cmake \
    ninja-build \
    pkg-config

# download Flutter SDK from Flutter Github repo
RUN git clone -b master https://github.com/flutter/flutter.git /sdk/flutter
RUN sudo chmod -R 777 /sdk/flutter
RUN sudo /sdk/flutter/bin/flutter --version
ENV PATH="/sdk/flutter/bin:${PATH}"