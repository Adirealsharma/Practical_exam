# Practical Exam CI/CD Pipeline

This repository contains the source code and the Jenkins pipeline configuration for the `Practical_exam` project.

## Overview

The project utilizes Jenkins for Continuous Integration and Continuous Deployment (CI/CD). The pipeline automates the process of building, testing, containerizing, and deploying a Dockerized application.

## Pipeline Stages

The Jenkinsfile (`jenkinsfile.groovy`) includes the following automated stages:

1. **Clone Repository:** Pulls the latest code from the `main` branch.
2. **Build:** Compiles and builds the application. *(Currently an echo placeholder)*
3. **Test:** Runs unit and integration tests. *(Currently an echo placeholder)*
4. **Docker Build:** Builds a Docker image named `cicd-demo` from the root Dockerfile.
5. **Deploy:** Runs the built Docker container, mapping port `9092` on the host to port `90` on the container in detached mode.

## Prerequisites

To run this pipeline successfully, ensure your Jenkins environment has the following installed and configured:
- Git
- Docker
- Jenkins (with the Pipeline plugin)
- A Windows build agent (the pipeline uses `bat` commands for Docker).

## Running Locally

If you want to build and run the Docker container locally without Jenkins, use the following commands:

```bash
docker build -t cicd-demo .
docker run -d -p 9092:90 cicd-demo
```

Once running, the application should be accessible at `http://localhost:9092`.