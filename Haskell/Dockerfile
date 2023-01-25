FROM ubuntu:23.04

RUN apt update
RUN apt upgrade -y
RUN apt install -y build-essential curl libffi-dev libffi8 libgmp-dev libgmp10 libncurses5-dev libncurses5 libtinfo5 \
    git sudo ack

# set the password later on
RUN adduser --disabled-password --gecos "Marco" marco
RUN usermod -aG sudo marco
WORKDIR /home/marco
USER marco
RUN mkdir -p /home/marco/workspace

#install ghcup
RUN curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh
RUN echo 'export PATH=$PATH:~/.ghcup/bin' >> .bashrc

USER root