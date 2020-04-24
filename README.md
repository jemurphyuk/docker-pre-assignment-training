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
- ``docker ps`` - show a list of running containers
