# CI/CD Pipeline for Go Web App: Demo Repository

[![license](https://img.shields.io/github/license/ybkuroki/go-webapp-sample?style=for-the-badge)](https://github.com/ybkuroki/go-webapp-sample/blob/master/LICENSE)
[![report](https://goreportcard.com/badge/github.com/ybkuroki/go-webapp-sample?style=for-the-badge)](https://goreportcard.com/report/github.com/ybkuroki/go-webapp-sample)
[![workflow](https://img.shields.io/github/actions/workflow/status/ybkuroki/go-webapp-sample/check.yml?label=check&logo=github&style=for-the-badge)](https://github.com/ybkuroki/go-webapp-sample/actions?query=workflow%3Acheck)

Welcome to the **CI/CD Pipeline Demo!** This project showcases how to containerize, continuously integrate, and deploy a Go web application using Docker and Jenkins. Below, you’ll find essential information to get started.

## Table of Contents

1.  Introduction
2.  Installation
4.  Project Structure
5.  Features
8.  Contributing
9.  License
10.  Contact

## Introduction

The **[go-webapp-sample](https://github.com/ybkuroki/go-webapp-sample)** is a simple web application written in Go. It demonstrates basic functionality and serves as a starting point for more complex projects. Our CI/CD pipeline ensures smooth development, testing, and deployment.

## Installation

To set up the project locally, follow these steps:

1.  Clone the repository:
    
    ```bash
    git clone https://github.com/MohamadYussef/Go-App-CICD-Pipeline.git
    cd Go-App-CICD-Pipeline
    
    ```
    
2.  Download and Install [Docker](https://docs.docker.com/engine/install/) 
3.  Download and Install [Jenkins](https://www.jenkins.io/doc/book/installing/) 
4. Download and Install [Golang](https://golang.org/)
    


## Starting Server

There are 2 methods for starting server.

  

### 1) On Host

1. Start Jenkins by running 

```bash

sudo systemctl start jenkins

```


2. Access [http://localhost:8080](http://localhost:8080) in your browser.

3. Login with the password ( you can find it in **/var/jenkins_home/secrets/initialAdminPassword**)
4. Install the [Docker Pipeline](Docker%20Pipeline) Plugin
5. Create a Pipeline Job and Configure it to get pipeline script from SCM and insert this repo URL
6. After running the build you should be able to access the app  on http://localhost:8000/

  

### 2) On Docker Container 

#### Starting Jenkins Server

1. Start a Jenkins server by running.( or use a [Docker-in-Docker image](https://hub.docker.com/_/docker) to use docker)

```bash

docker run -d -p 8080:8080  -v /usr/bin/docker:/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock --group-add=$(stat -c %g /var/run/docker.sock) jenkins/jenkins:lts-jdk17

```

2. Access [http://localhost:8080](http://localhost:8080) in your browser.

3. Download and Install [Golang](https://golang.org/) inside the container and then follow the same steps 


## Project Structure

The project structure is as follows:

```

- go-webapp-sample

+ config … Define configurations of this system.

+ logger … Provide loggers.

+ middleware … Define custom middleware.

+ migration … Provide database migration service for development.

+ router … Define routing.

+ controller … Define controllers.

+ model … Define models.

+ repository … Provide a service of database access.

+ service … Provide a service of book management.

+ session … Provide session management.

+ test … for unit test

- main.go … Entry Point.

- Dockerfile … Script used to create a Docker image.

- Jenkinsfile … Groovy script that defines a Jenkins Pipeline.

```

## Features

-   Minimalistic Go web application
-   Dockerized for easy deployment
-   Jenkins pipeline for CI/CD


## Contributing

We welcome contributions! To contribute:

1.  Fork the repository.
2.  Create a new branch.
3.  Make your changes.
4.  Submit a pull request.

## License

This project is licensed under the MIT License. See LICENSE for details.

## Contact

Feel free to reach out if you have any questions or feedback:

-   Email: Mohammad.Yussef@outlook.com 

Happy coding! 🚀👩‍💻