FROM ubuntu:22.04
LABEL maintainer="Khanh Tran <kxt1979@hotmail.com>"

RUN apt update && apt install -y openssl

WORKDIR /home

RUN echo openssl enc -aes-256-cbc -a -pbkdf2 -in file.txt -out file.base64.aes
RUN echo openssl enc -aes-256-cbc -d -a -pbkdf2 -in file.base64.aes -out file.decoded.txt
