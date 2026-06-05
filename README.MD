# Automated Container Build Pipeline

## Overview

This project demonstrates the fundamentals of containerization and automated build workflows using Docker and GitHub Actions.

The application is a simple Python Flask web application that displays a "Hello World" message. The application is containerized using Docker and integrated with GitHub Actions to automatically build the Docker image whenever code is pushed to the repository.

---

## Project Objectives

* Create a simple web application using Python Flask.
* Containerize the application using Docker.
* Build and run the application inside a Docker container.
* Automate the container build process using GitHub Actions.
* Demonstrate Continuous Integration (CI) practices.

---

## Technology Stack

* Python 3
* Flask
* Docker
* GitHub Actions
* GitHub

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

## Application

The Flask application exposes a single endpoint:

```http
GET /
```

Response:

```text
Hello World from Docker!
```

---

## Running the Application Locally

### 1. Create a Virtual Environment

```bash
python -m venv venv
```

### 2. Activate the Virtual Environment

Windows:

```bash
venv\Scripts\activate
```

Linux/macOS:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
python app.py
```

Open:

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

The application will be served from within the Docker container.

---

## GitHub Actions Workflow

The repository includes a GitHub Actions workflow that automatically executes whenever changes are pushed to the main branch.

Workflow Tasks:

1. Checkout repository code.
2. Set up Docker Buildx.
3. Build the Docker image.
4. Verify the build process.

This demonstrates a basic Continuous Integration (CI) pipeline for containerized applications.

---

## Workflow Trigger

The workflow is triggered on:

```yaml
on:
  push:
    branches:
      - main
```

---

## Learning Outcomes

Through this project, the following concepts were explored:

* Docker fundamentals
* Container image creation
* Dockerfile configuration
* Flask application deployment
* Git and GitHub workflow
* Continuous Integration (CI)
* GitHub Actions automation
* WSL2-based Docker environment on Windows

---

## Author

Anoop Kumar

Containerization and DevOps Assignment
