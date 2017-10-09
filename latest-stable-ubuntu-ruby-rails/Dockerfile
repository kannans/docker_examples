FROM ubuntu:latest
MAINTAINER Kannan S <kannanhudson@gmail.com>

RUN apt-get update

# Install ruby dependencies
RUN apt-get install -y nano wget links curl rsync bc git git-core apt-transport-https libxml2 libxml2-dev libcurl4-openssl-dev openssl sqlite3 libsqlite3-dev
RUN apt-get install -y gawk libreadline6-dev libyaml-dev autoconf libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
RUN apt-get install -y bzip2 g++ make zlib1g-dev libgmp-dev pkg-config libgmp-dev libssl-dev

RUN apt-get update

RUN gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

RUN \curl -sSL https://get.rvm.io | bash -s stable --ruby

ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN /bin/bash -l -c "rvm requirements"

RUN echo "gem: --no-document" > ~/.gemrc

RUN /bin/bash -l -c "gem install  bundler"
RUN /bin/bash -l -c "gem install  rails"