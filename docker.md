# Docker

## Installation

    sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    sudo apt-get -qq update
    sudo apt-get install docker-ce

    # add current user in group
    sudo usermod -a -G docker ${USER}

    sudo systemctl restart docker

    # You probably need to logout and re-login at this point

    # Verify
    docker run hello-world


## Configuration

Config doc is [here](https://docs.docker.com/engine/reference/commandline/dockerd//)

`/etc/docker/daemon.json`:

    {
        "dns": ["8.8.8.8", "8.8.4.4"]
    }

Restart the Docker daemon:

    sudo systemctl restart docker

## Manage images

List images:

    docker images

Delete image:

    docker rmi <image id>

Delete all images:
    
    docker images -q | xargs docker rmi

Run an image

    docker run <image-name>

Run an image interactively:

    docker run --rm -it --entrypoint=/bin/bash <image-name>

Delete all stopped containers:

    docker container prune

Major clean-up:

    $ docker system prune
    WARNING! This will remove:
        - all stopped containers
        - all networks not used by at least one container
        - all dangling images
        - all build cache



