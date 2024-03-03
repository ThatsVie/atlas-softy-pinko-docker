# Atlas - Softy Pinko Docker
This repository contains code for setting up horizontal scaling with Nginx and Docker as part of the Atlas Softy Pinko Docker project. The setup includes multiple API server instances and Nginx to distribute incoming requests among them.

## Prerequisites
Make sure you have Docker installed on your system. 

## Tasks Overview
**Task 0:** Setup Docker Environment

Set up a basic Docker environment and run a simple web server container.

**Task 1:** Static Content Proxy Server

Create a proxy server using Nginx to route requests to a static-content server.

**Task 2:** Dynamic Content API Server

Set up an API server using Flask to serve dynamic content and configure Nginx to proxy requests to it.

**Task 3:** Basic Load Balancing

Implement basic load balancing with Nginx to distribute incoming requests among multiple instances of the API server.

**Task 4:** Persistent Storage

Configure persistent storage for the API server using Docker volumes to ensure data integrity and availability.

**Task 5:** Container Orchestration

Use Docker Compose to orchestrate multiple containers and manage the dependencies between them effectively.

**Task 6:** Scale Horizontally

Achieve horizontal scaling by adding multiple instances of the API server and configuring Nginx to load balance requests between them using the Round-Robin algorithm.

## Usage
Once the setup is complete for each task, you can access the respective web application or API through the Nginx load balancer. Nginx will evenly distribute incoming requests among the available API server instances.
