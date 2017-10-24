# Dockerfiles

Use to build new Docker images.

## Setup 

Place a file named "Dockerfile" in its own directory.
Then use the path to the directory when building.

Let's assume that you've cd'ed to the dir, which means the path is '.'

## Build

    docker build .

    docker build --no-cache .

    docker build -t mytag .
