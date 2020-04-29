# Hackerank basic API Example

This project is to show a basic implementation of webscraping and generating JSON api data from live sources.

## Forked succesful and pulled

## Dockerfile
``FROM ubuntu:20.04

WORKDIR /home

COPY . .

RUN apt-get update && \
apt-get install -y git && \
apt-get install -y python3.8 && \
apt-get install -y python3-pip \

RUN pip install -r hackerank/requirements.txt

ENTRYPOINT ["python3.8"]`` - running python3.8 on previously installed
``CMD ["app.py"]`` -
