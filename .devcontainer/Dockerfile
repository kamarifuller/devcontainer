FROM mcr.microsoft.com/devcontainers/base:jammy

RUN sudo apt-get update
RUN apt-get install -y wget \
    xz-utils \
    file \
    zip

# download Flutter SDK from Flutter Github repo
RUN git clone -b master https://github.com/flutter/flutter.git /sdk/flutter