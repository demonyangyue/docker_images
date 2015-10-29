FROM ubuntu:14.04
RUN apt-get update
RUN apt-get install -y wget software-properties-common

# Install Python
RUN apt-get install -y python2.7 python2.7-dev

# Do following install tasks in /tmp
WORKDIR /tmp

# Install latest pip
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python2.7 get-pip.py

# Install other Python modules
RUN apt-get install -y build-essential pkg-config libpng-dev libfreetype6-dev

# Add a user (creating home and specifying shell) and
# use it when running the container
RUN useradd --create-home --shell /bin/bash yy
USER yy
WORKDIR /home/yy

# Add a yy storage directory
RUN mkdir -p /home/yy/store
ENV YY_STORES /home/yy/store
