# devcontainer

You can clone this repository into a container image or 
locally download this repository and open the folder in a container.
Either way, you need Visual Studio Code.

On M1 Macs Docker might throw errors building the container from either method. 
Docker may restart randomly or lose connection. I noticed the problems are resolved by
deleting old containers, images, volumes, and builds.

# Test Flutter web application

First, create your project via the terminal:
flutter create test_drive

Change into the project directory:
cd test_drive

Run your app on a web port and connect to it via your browser:
flutter run -d web-server --web-port [port number]
