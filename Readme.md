# Dockerized Node.js Application

This repository contains a Dockerfile to set up a Node.js application using the official Node.js Docker image based on Alpine Linux.

## Dockerfile

The Dockerfile in this repository uses the following base image:

``` bash
    FROM node:lts-alpine

    RUN mkdir /app
    WORKDIR /app
    COPY index.js index.js

    CMD node index.js
```

## Instructions

To build the Docker image and run the Node.js application:

1. Make sure you have Docker installed on your machine.
2. Clone this repository:

```bash
    git clone https://github.com/yourusername/your-repo.git
    cd your-repo
```
3. Build the Docker image using the provided Dockerfile:

```bash
    docker build -t node-app .
```

4. Run the Docker container:

```bash
    docker run -d -p 3000:3000 --name node-app node-app
```
The `-d` (detached) tag runs the container in the background, while the `-p` (port) tag lets you choose a port. Replace 3000 with the desired port for your application.

If you do not use the `-d` tag, press `CTRL + C` to stop the app.

5. Access the Node.js application in your web browser:

```bash
    http://localhost:3000
```
6. To stop the Docker container:

```bash
    docker stop node-app
```

## Pushing the Docker Image to Docker Hub

Assuming you have a Docker Hub account, to publish the Docker image to Docker Hub, follow these steps:

1. Login to Docker Hub:

```bash
    docker login
```

2. Tag the Docker image:

```bash
    docker tag node-app yourdockerhubusername/node-app:latest
```

3. 

```bash
    docker push yourdockerhubusername/node-app:latest
```

> Replace `yourdockerhubusername` with your Docker Hub username.

Now, your Docker image is pushed to Docker Hub and can be accessed by others.
