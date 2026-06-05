# Automated Container Build Pipeline

## Overview

This project demonstrates containerization and CI/CD automation using Docker, Docker Hub, GitHub, and GitHub Actions.

A simple Flask-based "Hello World" web application is containerized using Docker. GitHub Actions automatically builds and publishes the Docker image to Docker Hub whenever code is pushed to the main branch.

---

## Objectives

* Develop a simple Python Flask web application.
* Containerize the application using Docker.
* Automate image building using GitHub Actions.
* Publish container images to Docker Hub.
* Demonstrate Continuous Integration and Continuous Deployment (CI/CD) concepts.

---

## Technologies Used

* Python 3
* Flask
* Docker
* Docker Hub
* GitHub
* GitHub Actions
* WSL2

---

## Project Structure

```text
containerAssignment/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── README.md
│
└── .github/
    └── workflows/
        └── docker.yml
```

---

## Application Functionality

The application exposes a single endpoint:

```http
GET /
```

Response:

```text
Hello World from Docker!
```

---

## Running the Application Locally

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Application

```bash
python app.py
```

Access:

```text
http://localhost:5000
```

---

## Docker Containerization

### Build Docker Image

```bash
docker build -t hello-app .
```

### Run Docker Container

```bash
docker run -p 5000:5000 hello-app
```

Open:

```text
http://localhost:5000
```

---

## GitHub Actions CI/CD Workflow

This project uses GitHub Actions to automate the build and deployment process.

### Workflow Trigger

The workflow executes automatically whenever code is pushed to the `main` branch.

```yaml
on:
  push:
    branches:
      - main
```

### Workflow Steps

1. Checkout repository source code.
2. Configure Docker Buildx.
3. Authenticate with Docker Hub.
4. Build Docker image.
5. Push image to Docker Hub.
6. Report build status.

---

## CI/CD Pipeline

```text
Developer Pushes Code
           │
           ▼
     GitHub Repository
           │
           ▼
     GitHub Actions
           │
           ▼
     Docker Image Build
           │
           ▼
     Docker Hub Registry
```

---

## Docker Hub Repository

Container images are automatically published to Docker Hub.

Example image:

```text
docker pull <dockerhub-username>/<repository-name>:latest
```

---

## GitHub Secrets Used

The workflow uses repository secrets for secure authentication:

| Secret Name     | Purpose                 |
| --------------- | ----------------------- |
| DOCKER_USERNAME | Docker Hub username     |
| DOCKER_TOKEN    | Docker Hub access token |

---

## Learning Outcomes

Through this project, the following concepts were implemented:

* Docker Containerization
* Dockerfile Creation
* Container Image Management
* Git Version Control
* GitHub Repository Management
* GitHub Actions
* Docker Hub Integration
* Continuous Integration (CI)
* Continuous Deployment (CD)
* WSL2-based Development Environment

---

## Author

Anoop Kumar

Automated Container Build Pipeline Assignment
