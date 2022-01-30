# docker
Create various development environments using docker

build: 
    docker build -t ubuntu:dev1 \
            --build-arg USER_ID=$(id -u) \
            --build-arg USER_NAME=dev \
            --build-arg GROUP_ID=$(id -g) .

run: 
    docker run -it --rm -v ~/projects:/projects ubuntu:dev1 zsh


To avoid permission issue on shared files:
    https://vsupalov.com/docker-shared-permissions/
