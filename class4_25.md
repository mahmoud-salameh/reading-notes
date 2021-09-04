# Django REST Framework & Docker

## What is Docker?

__an open-source project that automates the deployment of software applications inside containers by providing an additional layer of abstraction and automation of OS-level virtualization on Linux.__

## Containers

Docker is really just Linux containers which are a type of virtualization.

Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.
## Components

The Docker software as a service offering consists of three components:

* Software: The Docker daemon, called dockerd, is a persistent process that manages Docker containers and handles container objects. The daemon listens for requests sent via the Docker Engine API.
* Objects: Docker objects are various entities used to assemble an application in Docker. The main classes of Docker objects are images, containers, and services. 



## Tools
1. Docker Compose is a tool for defining and running multi-container Docker applications. It uses YAML files to configure the application’s services and performs the creation and start-up process of all the containers with a single command.

2. Docker Compose (version 0.0.1) was released on December 21, 2013. The first production-ready version (1.0) was made available on October 16, 2014. Docker Swarm provides native clustering functionality for Docker containers, which turns a group of Docker engines into a single virtual Docker engine.

## Conclusion

* Docker is a way to run Linux containers
* Containers are a lightweight alternative to Virtual Machines
* Dockerfile is a list of instructions for creating an image
* Images are made up of one or more layers
* Containers are a running instance of an image
* docker-compose.yml controls how to run the container
* Containers are stateless and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases (which we didn’t cover here).
