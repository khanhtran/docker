# docker
Create various development environments using docker

build: 
    docker build -t kxtdev/ubuntu:dev-base \
            --build-arg USER_ID=$(id -u) \
            --build-arg USER_NAME=dev \
            --build-arg GROUP_ID=$(id -g) .

run: 
    docker run -it --rm -v ~/projects:/projects kxtdev/ubuntu:dev-base zsh

Notes:
    - to be able to push to docker, the image name must be: <hub-userid>/image-name:tag (tag is optional)    
    - To avoid permission issue on shared files:
        https://vsupalov.com/docker-shared-permissions/
