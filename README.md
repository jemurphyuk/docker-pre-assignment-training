# Docker

## What is Docker
Docker is an open source software for the automated deployment of applications inside containers. Docker provides and additional layer of abstraction and automation of operating system virtualisation, such as Linux. Use of Docker means an application can be packaged with all of its dependencies into a standardised unit. Unlike a virtual machine, containers have lower overheads and enable more efficient usage of system and resources

Docker enables virtual machines with different operating software communicate with one another

## Containers
Isolation in VMs gives a high computational overhead, containers leverage low-level mechanics of the host OS.
Containers offer a packaging mechanism in which applications can be abstracted from running environment. This decoupling allow apps to deployed consistently regardless of whether target environment is a private data centre or public cloud, making environments that can be run anywhere.

## Why use Docker?
Communication across OS, using multiple containers which can be booted up as needed in the event of a crashvag

### Terminology
- Images - blueprints of application which form basis of containers
- Containers - created from Docker images and run app
- Docker Daemon - background service running on the host that manages container building, running and distribution. Manages hard drive space, images and networks. Works with rest images and uses a user friendly API
- Docker Client - command line tool allows user to interact with Daemon
  - Kitematic - client used to provide GUI to the user
- Docker Hub - registry of Docker images

### Commands
- ``docker pull`` - command to download an image
- ``docker run`` - run application from images
  - ``docker run --rm`` - run function that automatically deletes container once exited
  - ``docker run --name [OWN_NAME] [IMAGE_ID]`` - give own name to container
- ``docker ps`` - show a list of running containers, with  ``-a`` for containers that have been run
- ``docker rmi`` - remove an image
- ``docker rm`` - remove containers once they are finished (this will prevent usage of disk space)
  - ``docker rm $(docker ps -a -q -f status=exited)`` - will remove all containers that have a status of exited, with ``-q`` returning the numeric IDs to delete and ``-f`` to filter output based on conditions
  - ``docker container prune`` is also available to achieve same results as above in new docker builds
- ``docker port [CONTAINER]`` - view running ports
- ``docker images`` - list of images available locally
- ``:latest`` - tag that is automatically added to show latest version, can add own tags for previous versions
- ``docker stop [NAME]`` - stop container but not destroy

## Using VirtualBox and Vagrant to avoid need for 10 Pro and Hyper-V
Use VirtualBox/Vagrant to create Linux virtual machine to run install and run docker on
- Virtualisation on host operating system will take resources to run the guest system
- VM conditions can be seen in Vagrantfile

### Docker specific commands run in training
docker pull nginx and docker run nginx with name and port detached
Container must have open port
- ``-d`` - detached service to keep container open
- ``-p [GUEST:HOST]`` - port flag to show open ports
Execute commands to docker container
- ``docker exec [CONTAINER] 'command'`` - execute command in nginx container
- ``docker run -d --name nginx_james -v /www/data/:/vagrant/ -p 80:80 nginx`` - didnt appear to share folder
- ``docker run -itd --name....`` - interactive container, ubuntu server within a container
