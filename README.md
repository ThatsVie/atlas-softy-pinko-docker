# Atlas - Softy Pinko Docker

This project demonstrates the setup of a Dockerized environment for a web application comprising front-end, back-end, and proxy servers. It encompasses tasks from 0 to 6, each focusing on different aspects of containerization, deployment, and scalability.

## Prerequisites

Before getting started, ensure you have Docker installed on your system. You can download and install Docker from the official website: [Docker](https://www.docker.com/get-started).

## Project Structure

The project is structured into multiple tasks, each contained within its own directory:

- **task0:** Setting up a basic Docker environment.
- **task1:** Dockerizing a simple web application.
- **task2:** Building Docker images for front-end and back-end services.
- **task3:** Using Docker Compose to manage multiple containers.
- **task4:** Setting up a reverse proxy with Nginx.
- **task5:** Implementing horizontal scaling with Docker Compose.
- **task6:** Scaling horizontally with multiple API servers and Nginx load balancing.

## Tasks Overview

### Task 0: Setup Docker Environment

Initialize a basic Docker environment by installing Docker Desktop. Create a Docker image using a Dockerfile based on the latest Ubuntu distribution. Upon running a container from this image, it will echo "Hello, World!" in the terminal.

### Task 1: Dockerizing a Simple Web Application

Set up a Flask-based back-end within a Docker container. The back-end consists of a Flask server hosting one endpoint that returns "Hello, World!" when called.

### Task 2: Dynamic Content API Server

Set up the front-end for the Softy Pinko project, including reorganizing the project directory, setting up a static web server using Nginx, and configuring it to serve front-end content.

### Task 3: Basic Load Balancing

Connect the front-end to the back-end of the Softy Pinko project, enabling dynamic data on the front-end. This involves communication between two Docker images, each running in its own Docker container.

### Task 4: Persistent Storage

Simplify the management of application components by using Docker Compose. Define and manage multi-container Docker applications with a single configuration file, reducing complexity and streamlining the process of spinning up multiple Docker containers.

### Task 5: Container Orchestration

Implement a proxy server using Nginx to serve as an intermediary between the client and the application's front-end and back-end servers. This simplifies client-side configuration and decouples the client from the specific locations of the application's components.

### Task 6: Scale Horizontally

Address the scenario where traffic to the site increases significantly, potentially overwhelming the API server. Set up multiple API servers and use Nginx for load balancing between them. Launch Docker containers to have two or more API servers, with Nginx acting as a load balancer using the Round-Robin algorithm.


## Usage

Follow these steps to run each task and access the deployed web application or API:

### Cloning the Repository

1. Clone this repository to your local machine using the following command:
```bash
git clone
```
### Task 0: Setup Docker Environment

1. Navigate to the `task0` directory.
2. Run the command `docker-compose up --build` to build the Docker image and start the container.
3. Open a web browser and go to `http://localhost:5000` to view the "Hello, World!" message.

### Task 1: Dockerizing a Simple Web Application

1. Navigate to the `task1` directory.
2. Run the command `docker-compose up --build` to build the Docker image and start the container.
3. Open a web browser and go to `http://localhost:5000` to view the Flask application's endpoint.

### Task 2: Dynamic Content API Server

1. Navigate to the `task2` directory.
2. Run the command `docker-compose up --build` to build the Docker images and start the containers.
3. Open a web browser and go to `http://localhost:80` to view the static web server serving the front-end content.

### Task 3: Basic Load Balancing

1. Navigate to the `task3` directory.
2. Run the command `docker-compose up --build` to build the Docker images and start the containers.
3. Open a web browser and go to `http://localhost:80` to view the front-end content, which communicates with the back-end API.

### Task 4: Persistent Storage

1. Navigate to the `task4` directory.
2. Run the command `docker-compose up --build` to build the Docker images and start the containers.
3. Open a web browser and go to `http://localhost:80` to view the front-end content.

### Task 5: Container Orchestration

1. Navigate to the `task5` directory.
2. Run the command `docker-compose up --build` to build the Docker images and start the containers.
3. Open a web browser and go to `http://localhost:80` to view the front-end content.

### Task 6: Scale Horizontally

1. Navigate to the `task6` directory.
2. Run the command `docker-compose up --build` to build the Docker images and start the containers.
3. Open a web browser and go to `http://localhost:80` to view the front-end content. Reload the page multiple times to observe the load balancing between multiple API servers.
