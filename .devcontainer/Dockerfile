FROM dorowu/ubuntu-desktop-lxde-vnc:focal

RUN sudo apt update

RUN sudo apt install -y git

# Install rbenv and ruby-build
RUN mkdir ~
RUN echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
ENV PATH="$HOME/.rbenv/bin:$HOME/.rbenv/shims:$PATH"
RUN wget -q https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer -O- | bash

# Update Path
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc

# Install ruby
RUN sudo apt install -y zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev
RUN rbenv install 2.6.6 
RUN rbenv global 2.6.6

# Install rails
RUN apt install -y nodejs
RUN apt install -y npm
RUN npm install -g npm
RUN npm install yarn -g
RUN /home/ubuntu/.rbenv/shims/gem install --no-document rails -v 6.0.3

# Install dev dependencies
RUN gem install rubocop
RUN gem install solargraph
RUN gem install yard

# Install apt packages / gems below
# RUN apt install -y packages
# RUN gem install gemname
RUN gem install middleman

# Configure VNC Server
# ENV RESOLUTION="1920x1080"

RUN apt-get update
RUN apt-get install -y locales locales-all

ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
