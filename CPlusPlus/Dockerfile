FROM ubuntu:23.04

RUN apt update
RUN apt upgrade -y
RUN apt install -y build-essential curl git sudo ack locales

RUN locale-gen en_US.UTF-8
RUN update-locale LANG=en_US.UTF-8

WORKDIR /root
RUN mkdir workspace
