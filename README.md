# Docker

## What is Docker
Docker is an open source software for the automated deployment of applications inside containers. Docker provides and additional layer of abstraction and automation of operating system virtualisation, such as Linux. Use of Docker means an application can be packaged with all of its dependencies into a standardised unit. Unlike a virtual machine, containers have lower overheads and enable more efficient usage of system and resources

## Containers
Isolation in VMs gives a high computational overhead, containers leverage low-level mechanics of the host OS.
Containers offer a packaging mechanism in which applications can be abstracted from running environment. This decoupling allow apps to deployed consistently regardless of whether target environment is a private data centre or public cloud, making environments that can be run anywhere.

### Terminology
- Images - blueprints of application which form basis of containers
- Containers - created from Docker images and run app
- Docker Daemon - background service running on the host that manages container building, running and distribution
- Docker Client - command line tool allows user to interact with Daemon
  - Kitematic - client used to provide GUI to the user
- Docker Hub - registry of Docker images

### Commands
- ``docker pull`` - command to download an image
- ``docker run`` - run application from images
  - ``docker run --rm`` - run function that automatically deletes container once exited
- ``docker ps`` - show a list of running containers, with  ``-a`` for containers that have been run
- ``docker rm`` - remove containers once they are finished (this will prevent usage of disk space)
  - ``docker rm $(docker ps -a -q -f status=exited)`` - will remove all containers that have a status of exited, with ``-q`` returning the numeric IDs to delete and ``-f`` to filter output based on conditions
  - ``docker container prune`` is also available to achieve same results as above in new docker builds
- ``docker port [CONTAINER]`` - view running ports
- ``docker images`` - list of images available locally

## Using VirtualBox and Vagrant to avoid need for 10 Pro and Hyper-V
