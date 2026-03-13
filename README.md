# Docker Mastery Assignment

This repository contains the Docker project for the Docker Mastery Assignment. The project demonstrates building, running, and deploying a Flask application using Docker, Docker Compose, and multiple container registries (DockerHub, GHCR, AWS ECR, and Azure ACR).

---

## Table of Contents
1. Project Overview
2. Technologies Used
3. Docker Images
4. Running the Project Locally
5. Challenges and Solutions
6. Screenshots


---

## Project Overview

This project is a **full-stack Flask application** that interacts with Redis and PostgreSQL. Docker was used to containerize each component to simplify deployment. GitHub Actions was configured to automatically build and push Docker images to GitHub Container Registry (GHCR).

---

## Technologies Used

- Docker  
- Docker Compose  
- Flask (Python)  
- Redis  
- PostgreSQL  
- GitHub Actions  
- AWS ECR  
- Azure Container Registry (Bonus)

---

## Docker Images

### 1. DockerHub Image
https://hub.docker.com/r/cwamie/flask-app

### 2. GHCR Image
ghcr.io/Mhariogh/flask-app:latest

### 3. AWS ECR Repository URI
901481721710.dkr.ecr.us-east-1.amazonaws.com/flask-app:latest

### 4. Azure Container Registry (Bonus)
stephendockerassign.azurecr.io/flask-app:v1.0

---

## Running the Project Locally

To start the project locally, use Docker Compose
' docker compose up --build -d  '

This will:
Build all images
Start the Flask app, Redis, and PostgreSQL containers

Run in detached mode
To stop the project:
'docker compose down '


Challenges and Solutions

1. GitHub Actions Workflow Errors

Issue: Workflow failed to push images to GHCR due to incorrect repository naming.

Solution: Used ${{ github.repository_owner }} instead of hardcoding my username.

2. Docker Image Push Issues

Issue: Authentication errors while pushing to DockerHub.

Solution: Logged in using docker login with correct credentials.

3. AWS ECR Authentication

Issue: Docker could not authenticate to ECR.

Solution: Ran aws ecr get-login-password and piped it to docker login.

4. ACR Push Formatting Issues

Issue: Docker tag command formatting caused errors.

Solution: Ensured the full registry path was on a single line.

