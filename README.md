# Cloud service demo
## Purpose
The purpose of this project is to get experience with Git and GitHub

## How version control helps cloud projects
Version control helps cloud projects by allowing the DevOps engineer to easily revert changes that were made and also keep track of who made what changes.

## What is Docker?
Docker is a system that allows you to run "mini computers" on your system. More specifically it lets you run Docker images and containers to host applications or code.

## What is a Docker image?
A Docker image is a file that holds the configuration and settings for a Docker container. This file will hold the type of OS and version as well other settings like port forwarding.

## What is a Docker container?
A Docker container is what runs the Docker images. A Docker container can be thought of as something like a lightweight VM in a sense.

## How to build and run your application using Docker
To build the Docker image run the following command
```bash
docker build -t cloud-service-demo:1.0 .
```

To then run the image you just built run this command
```bash
docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0
```