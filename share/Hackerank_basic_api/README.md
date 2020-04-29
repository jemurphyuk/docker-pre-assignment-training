# Hackerank basic API Example

This project is to show a basic implementation of webscraping and generating JSON api data from live sources.

## Forked succesful and pulled

## Dockerfile
``docker build . -t james-docker-image`` - command to build image using Dockerfile as a provisioner

````
FROM ubuntu:20.04

WORKDIR /home/Hackerank_basic_api

COPY . .

RUN apt-get update && \
apt-get install -y git && \
apt-get install -y python3.8 && \
apt-get install -y python3-pip \

RUN pip install -r requirements.txt

ENTRYPOINT ["python3.8"]
````
- running python3.8 on previously installed, configures a container that will run as an executable
````
CMD ["app.py"]
````
- running command to set default command when docker runs container
