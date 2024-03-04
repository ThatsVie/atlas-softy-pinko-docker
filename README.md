# Atlas - Softy Pinko Docker
This repository contains code for setting up horizontal scaling with Nginx and Docker as part of the Atlas Softy Pinko Docker project. The setup includes multiple API server instances and Nginx to distribute incoming requests among them.

## Prerequisites
Make sure you have Docker installed on your system. You can download and install Docker from the official website: [Docker](https://www.docker.com/get-started).

## Tasks Overview
**Task 0:** Setup Docker Environment

In this task we create a Docker image using a Dockerfile. The Docker image is based on the latest Ubuntu distribution, and upon running a container from this image, it will echo "Hello, World!" in the terminal.

**Task 1:** Static Content Proxy Server

Here we set up a Flask-based back-end within a Docker container. The back-end consists of a Flask server hosting one endpoint that returns "Hello, World!" when called.

**Task 2:** Dynamic Content API Server

Here we set up the front-end for the Softy Pinko project. This involves reorganizing the project directory, setting up a static web server using Nginx, and configuring it to serve the front-end content.

**Task 3:** Basic Load Balancing

In this task we connect the front-end to the back-end of the Softy Pinko project,enabling dynamic data on our front-end. This involves communication between two Docker images, each running in its own Docker container.

**Task 4:** Persistent Storage

In this task we simplify the management of our application components by using Docker Compose. Docker Compose allows us to define and manage multi-container Docker applications with a single configuration file. This reduces complexity and streamlines the process of spinning up multiple Docker containers.

**Task 5:** Container Orchestration

Here we implement a proxy server using Nginx to serve as an intermediary between the client and our application's front-end and back-end servers. This allows us to simplify the client-side configuration and decouples the client from the specific locations of the application's components.

**Task 6:** Scale Horizontally

Finally, we address the scenario where the traffic to your site increases significantly, potentially overwhelming your API server. To handle this situation, we will set up multiple API servers and use Nginx for load balancing between them. The goal is to launch Docker containers such that we have two or more API servers. Nginx will act as a load balancer, distributing incoming requests among these servers using the Round-Robin load-balancing algorithm.

## Usage
Once the setup is complete for each task, we can access the respective web application or API through the Nginx load balancer. Nginx will evenly distribute incoming requests among the available API server instances.
