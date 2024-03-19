
# Devcontainer Environment

### Introduction
A **devcontainer** is a **portable**, **configurable**, **reproducable**, **lightweight** virtualized environment. Using a container we excercise a great deal of control **minimizing variability** which may result in unexpected behaviours. We can **quickly** start an environmemt for Flutter app development with all dependencies.

---

### Configuration
The container is built using the [devcontainer.json](../.devcontainer/devcontainer.json) and [Dockerfile](../.devcontainer/Dockerfile).

[**Base Image**: Ubuntu (jammy)](../.devcontainer/Dockerfile#L<1>)

### Tools
Inside the [Dockerfile](../.devcontainer/Dockerfile) we use the following to install tools and dependencies.

    RUN apt-get update && apt-get install -y \
        wget \
        xz-utils \
        file \
        zip \
        openjdk-17-jdk-headless --no-install-recommends \
        clang \
        cmake \
        ninja-build \
        pkg-config \
        libgtk-3-dev \
        git

### Integration with VS Code

In the [devcontainer.json](../.devcontainer/devcontainer.json#L<14>) we use VS Code extensions to get Dart and Flutter language support for sytax in the editor.

## How to Use

1. Start Docker Desktop
2. Open VS Code
3. Use ```command+shift+p``` and type **Dev Containers**

Select one of the following: ***clone this repository into a container image*** or 
***locally download this repository and open the folder in a container***.

### Challenges and Solutions

Sometimes the build fails though it was previously successful. If using Apple Silicon ensure Rosetta is installed and up-to-date by running the following on the command line:

```softwareupdate --install-rosetta```

If Docker continues to fail builds, restart randomly, or lose connection. I noticed the problems are resolved by deleting old containers, images, volumes, and builds.

If this doesnt work try increasing the memory resources Docker can use.

# Test Flutter web application

First, create your project via the terminal:

```flutter create test_drive```

Change into the project directory:

```cd test_drive```

Run your app on a web port and connect to it via your browser:

```flutter run -d web-server --web-port [port number]```

# Conclusion

Ultimately using the Decontainer made it possible to quickly start a reproducable development environment that is easily sharable. The configuration steps are automated and are easily changed if needed.