# Container base image
FROM ubuntu:latest

# Update APT using apt-get update
RUN apt-get update

# Upgrade currently installed software through APT using apt-get upgrade -y
RUN apt-get upgrade -y

# Install python3, python3-pip, and flask
RUN apt-get install -y python3 python3-pip
RUN pip3 install flask

# /app as the working directory
WORKDIR /app

# 
