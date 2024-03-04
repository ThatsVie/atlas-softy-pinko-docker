# Atlas - Softy Pinko Docker
This repository contains code for setting up horizontal scaling with Nginx and Docker as part of the Atlas Softy Pinko Docker project. The setup includes multiple API server instances and Nginx to distribute incoming requests among them.

## Prerequisites
Make sure you have Docker installed on your system. 

## Tasks Overview
**Task 0:** Setup Docker Environment

In this task we create a Docker image using a Dockerfile. The Docker image is based on the latest Ubuntu distribution, and upon running a container from this image, it will echo "Hello, World!" in the terminal.

**Task 1:** Static Content Proxy Server

Here we set up a Flask-based back-end within a Docker container. The back-end consists of a Flask server hosting one endpoint that returns "Hello, World!" when called.

**Task 2:** Dynamic Content API Server

Here we set up the front-end for the Softy Pinko project. This involves reorganizing the project directory, setting up a static web server using Nginx, and configuring it to serve the front-end content.

**Task 3:** Basic Load Balancing

In this task we connect the front-end to the back-end of the Softy Pinko project, allowing dynamic data exchange between the two Docker containers.

**Task 4:** Persistent Storage

Configure persistent storage for the API server using Docker volumes to ensure data integrity and availability.

**Task 5:** Container Orchestration

Use Docker Compose to orchestrate multiple containers and manage the dependencies between them effectively.

**Task 6:** Scale Horizontally

Achieve horizontal scaling by adding multiple instances of the API server and configuring Nginx to load balance requests between them using the Round-Robin algorithm.

## Usage
Once the setup is complete for each task, you can access the respective web application or API through the Nginx load balancer. Nginx will evenly distribute incoming requests among the available API server instances.
