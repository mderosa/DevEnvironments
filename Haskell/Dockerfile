FROM ubuntu:23.04

RUN apt update
RUN apt upgrade -y
RUN apt install -y build-essential curl libffi-dev libffi8 libgmp-dev libgmp10 libncurses5-dev libncurses5 libtinfo5 \
    git sudo ack locales

RUN locale-gen en_US.UTF-8
RUN update-locale LANG=en_US.UTF-8

#install ghcup
RUN curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh
WORKDIR /root
RUN .ghcup/bin/ghcup install hls


RUN echo 'export PATH=$PATH:~/.ghcup/bin' >> .bashrc
RUN mkdir workspace
