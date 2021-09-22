# cubemos-docker

Dockerfile and image for [Cubemos sdk](https://www.cubemos.com/skeleton-tracking-sdk) and ubuntu 18.04

This repository provides a Dockerfile (and associated image hosted in the GitHub `ghcr` registry).

In order to use it please proceed as follows:

1. Pull the docker image:
    ```console
    docker pull ghcr.io/giulioromualdi/cubemos-docker:latest
    ```
2. Launch the container:
    ```console
    docker run -it --user user --env="DISPLAY" --net=host --device /dev/dri ghcr.io/giulioromualdi/cubemos-docker:latest
    ```
    
    
:warning: In order to use cubemos you have to set your activation key
