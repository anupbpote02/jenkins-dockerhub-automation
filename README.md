# Jenkins DockerHub Automation Pipeline

This repository demonstrates a **Jenkins Declarative Pipeline** that automates building and deploying Docker images to Docker Hub using stored credentials.

## 📁 Files
- **Dockerfile** – Creates a simple Ubuntu-based Docker image.
- **Jenkinsfile** – Defines pipeline stages for build and deploy.

## ⚙️ Pipeline Stages
1. **Git Checkout** – Clones the repository from source control.
2. **Build Image** – Builds the Docker image using the `Dockerfile` and tags it.
3. **Deploy Image** – Pushes the image to Docker Hub using Jenkins credentials (`dockerhub_id`).

## 🧰 Tools Used
- Jenkins
- Docker
- Docker Hub
- Groovy (Declarative Pipeline)

---
*Automating Docker image build and deployment using Jenkins and Docker Hub credentials.*
