FROM ubuntu:24.04

RUN apt update
RUN apt upgrade -y
RUN apt install -y curl git sudo ack locales libssl-dev build-essential 

RUN locale-gen en_US.UTF-8
RUN update-locale LANG=en_US.UTF-8

WORKDIR /root
RUN mkdir workspace

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
ENV NVM_DIR=/root/.nvm
RUN . "$NVM_DIR/nvm.sh" && nvm install --lts
# Use the installed version of Node.js as the default version for the container
RUN . "$NVM_DIR/nvm.sh" && nvm use --lts


