# Using this fprime-docker
## Prerequisites
Docker must be installed on your system.  See [Docker Installation](https://docs.docker.com/engine/installation/) for more information. Visual Studio Code is also recommended for development for attaching to the docker container.  See [Visual Studio Code](https://code.visualstudio.com/) for more information.

## Setup the docker container
1. Clone the F` project into a directory of your choice.
2. Run `docker pull ghcr.io/nu-horizonsat/fprime-docker:main` to pull the docker image.
3. Run `docker run -it -v <path to fprime project>:/root/project ghcr.io/nu-horizonsat/fprime-docker:main` to start the docker container.  This will mount the fprime project directory to the docker container.  This will allow you to edit the files on your host machine and run the build from the docker container.
4. Open Visual Studio Code and install the [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension.
5. Press Ctrl+Shift+P and select `Remote-Containers: Attach to Running Container...` and select the container that you started in step 3.
6. Using Visual Studio Code, open the `/root/project` directory.
7. Open a terminal in Visual Studio Code and run `fprime-util generate` to generate the build files and `fprime-util build -j4` to build the project.

The docker container also contains fprime-gds.
