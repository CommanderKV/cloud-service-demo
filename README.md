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

# Kubernetes

## What kubernetes is and why it is used
Kubernetes is used to manage deployments of containers (or pods) in a containarized application.

## The purpose of a Pod, Deployment, and Service

### Pod
The purpose of a pod is to run the image / container itself. A pod contains the actual code that is being executed.

### Deployment

A deployment's purpose is to maanage the lifecycle of pods. It defines the lifecycle of the pod in terms of spinning up and spinning down the pods.

### Service

A service's purpose is to enable a consistent constant endpoint that can be accessed.

## How to start Minikube and make docker images available

To start minikube run the following command
```bash
minikube start --driver=docker
```

Now to make docker images availabile we must load the images into minikube. To load our program into 
minikube run the following command
```bash
minikube image load cloud-service-demo:1.0
```

## How to apply the Deployment and Service YAML files

To apply the deployment and service yaml files run the following command
```bash
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
```

## How to access the application using kubectl port-forward

To access the application using port forwarding run the following command
```bash
kubectl port-forward service/cloud-service-demo 8080:80
```
This will make the application available at https://localhost:8080

## Useful commands
```bash
minikube start --driver=docker
minikube image load cloud-service-demo:1.0
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
kubectl port-forward service/cloud-service-demo 8080:80
```