# Atlas - Softy Pinko Docker

This project demonstrates the setup of a Dockerized environment for a web application comprising front-end, back-end, and proxy servers. It encompasses tasks 0 to 6, each focusing on different aspects of containerization, deployment, and scalability.

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

Set up the front-end for the Softy Pinko project, including cloning this repository: [Softy Pinko Front-end Repository](https://github.com/atlas-school/softy-pinko-front-end), reorganizing the project directory, setting up a static web server using Nginx, and configuring it to serve front-end content.

**Note:** To ensure easy editing and management of the cloned repository, it was initially copied to a different directory, given a different name, and then the original repository was deleted. Finally, the copied repository was renamed with its original name. This approach allowed for seamless integration of the cloned repository within the project.

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

Clone this repository to your local machine using the following command:
```bash
git clone https://github.com/ThatsVie/atlas-softy-pinko-docker.git
```
### Task 0:

1. Navigate to the `task0` directory.
   ```bash
   cd atlas-softy-pinko-docker/task0
   ```
2. Run the following command to build the Docker image using the Dockerfile:
   ```bash
   docker build -t softy-pinko:task0 .
   ```
3. Once the image is built, run the Docker container using the following command:
   ```bash
   docker run -it --rm --name softy-pinko-task0 softy-pinko:task0
   ```
4. You should see "Hello, World!" printed in the terminal, indicating that the container is running successfully.

### Task 1

1. Navigate to the `task1` directory.
   ```bash
   cd atlas-softy-pinko-docker/task1
   ```
2. Use the following commands in the terminal to build and run your Docker image:
   ```bash
   docker build -f ./Dockerfile -t softy-pinko:task1 .
   docker run -p 5252:5252 -it --rm --name softy-pinko-task1 softy-pinko:task1
   ```
   The -p 5252:5252 flag maps port 5252 of the Docker container to port 5252 of the host machine, allowing you to access the Flask application from your local environment.

3. Once the Docker container is running, open a web browser and navigate to `http://localhost:5252/api/hello`. You should see the "Hello, World!" message displayed in the browser.

### Task 2:

1. Navigate to the `task2` directory.
   ```bash
    cd atlas-softy-pinko-docker/task2
   ```
2. Use the following commands in the terminal to build and run your Docker image:
   ```bash
   docker build -f ./front-end/Dockerfile -t softy-pinko-front-end:task2 ./front-end
   docker run -p 9000:9000 -it --rm --name softy-pinko-front-end-task2 softy-pinko-front-end:task2
   ```
3. Once the Docker container is running, open a web browser and navigate to `http://localhost:9000`. You should see the Softy Pinko front-end website displayed in the browser.

### Task 3:
   **Note: Before starting Task 3, ensure that you stop any running instances of Task 2. Since both Task 2 and Task 3 involve front-end applications, they use the same port for hosting the front-end content. Failing to stop Task 2 might result in port conflicts, causing issues with accessing the front-end of Task 3.**
   
1. Navigate to the `task3` directory.
   ```bash
    cd atlas-softy-pinko-docker/task3
   ```
2. Navigate to the task3/back-end directory. Then, build and run the Docker image for the back-end:
   ```bash
   docker build -f ./Dockerfile -t softy-pinko-back-end:task3 .
   docker run -p 5252:5252 -it --rm --name softy-pinko-back-end-task3 softy-pinko-back-end:task3
   ```
3. Open another terminal and navigate to the task3/front-end directory. Then, build and run the Docker image for the front-end:
   ```bash
   docker build -f ./Dockerfile -t softy-pinko-front-end:task3 .
   docker run -p 9000:9000 -it --rm --name softy-pinko-front-end-task3 softy-pinko-front-end:task3
   ```
4. Once both Docker containers are running, open a web browser and navigate to `http://localhost:9000`. You should see the Softy Pinko front-end website with dynamic content retrieved from the back-end API.

### Task 4:
   **Note: Before running docker-compose up for Task 4, please ensure that you have stopped any running containers from Task 3. Since Task 3 and Task 4 use the same ports, failing to stop Task 3 containers may result in port conflicts, leading to errors like:**
   
   ```bash
   Error response from daemon: driver failed programming external connectivity on endpoint task4-front-end-1: Bind for 0.0.0.0:9000 failed: port is already allocated

   Error response from daemon: driver failed programming external connectivity on endpoint task4-back-end-1: Bind for 0.0.0.0:5252 failed: port is already allocated
   ```
1. Open a new terminal and navigate to the `task4` directory.
   ```bash
    cd atlas-softy-pinko-docker/task4
   ```
2. Use the following commands
   ```bash
   docker-compose build
   docker-compose up
   ```
3. Open a web browser and go to `http://localhost:80` to view the front-end content.

### Task 5:

1. Open a new terminal and navigate to the `task5` directory.
   ```bash
    cd atlas-softy-pinko-docker/task5
   ```
2. Use the following commands
   ```bash
   docker-compose build
   docker-compose up
   ```
3. Access the application via `http://localhost:80` in your browser, which is now routed through the proxy server.

### Task 6:

1. Open a new terminal and navigate to the `task6` directory.
   ```bash
    cd atlas-softy-pinko-docker/task6
   ```
2. Run command
   ```bash
   docker-compose up --scale back-end=2
   ```
4. Open a web browser and go to `http://localhost:80` to view the front-end content. Reload the page multiple times and check the terminal output to see how requests are being load-balanced between the two API servers. The back-end server that the Nginx load balancer routes to should alternate between task6-back-end-1 and task6-back-end-2.
