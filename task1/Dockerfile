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

# Copy api.py from the host to /app in the container
COPY ./api.py /app/api.py

# Expose port 5252 to allow external access
EXPOSE 5252

# Command to run the Flask application
CMD ["python3", "api.py"]
