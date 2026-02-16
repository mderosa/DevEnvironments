FROM ubuntu:24.04

RUN apt update
RUN apt upgrade -y
RUN apt install -y build-essential curl git sudo ack zlib1g-dev libssl-dev libncurses-dev libbz2-dev libffi-dev \
    libreadline-dev libsqlite3-dev liblzma-dev locales
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata

RUN apt install -y libpq-dev

RUN locale-gen en_US.UTF-8
RUN update-locale LANG=en_US.UTF-8

WORKDIR /root
RUN mkdir workspace

# setup pyenv
RUN curl https://pyenv.run | bash
RUN echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
RUN echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc
RUN echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
RUN echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
RUN echo 'eval "$(pyenv init -)"' >> ~/.profile

# install python 3.14.3
RUN /root/.pyenv/bin/pyenv install 3.14.3
RUN /root/.pyenv/bin/pyenv global 3.14.3

# setup pipenv
RUN /root/.pyenv/shims/pip install --user pipenv
RUN echo 'export PATH=$PATH:~/.local/bin' >> ~/.bashrc