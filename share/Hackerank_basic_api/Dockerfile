FROM ubuntu:20.04

WORKDIR /home/Hackerank_basic_api/

COPY . .

RUN apt-get update && \
apt-get install -y git && \
apt-get install -y python3.8 && \
apt-get install -y python3-pip

RUN pip3 install -r requirements.txt

ENTRYPOINT ["python3.8"]

CMD ["app.py"]
