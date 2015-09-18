# Disclaimer

This repository is intended to store some [Docker](https://www.docker.com/)
experiments. Use them at your own risk ;)

# Building images

To build any image, just cd into the corresponding directory and run [docker
build](https://docs.docker.com/reference/commandline/build/). For example:

    cd dockerfiles/jenkins-slave
    sudo docker build --rm -t jenkins-slave .
