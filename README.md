# Dockerized Node.js Application with AWS ECR

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-E23237?style=flat&logo=amazon-aws&logoColor=white)

## Project Overview
This project demonstrates how to **Dockerize a Node.js application** and push it to a **private Docker registry using AWS Elastic Container Registry (ECR)**.  

It covers:
- Writing a Dockerfile for a Node.js application
- Building and running Docker images locally
- Creating a private Docker repository in AWS ECR
- Pushing Docker images to AWS ECR

---

## Technologies Used
- **Node.js** – Backend application runtime  
- **Docker** – Containerization platform  
- **Amazon ECR** – Private Docker registry  

---

## Project Structure
```bash
project-root/
│
├── app.js              # Main Node.js application
├── package.json        # Node.js dependencies
├── Dockerfile          # Docker image build instructions
└── README.md           # Project documentation
```

---

## Steps to Run Locally

### 1. Build Docker Image

    docker build -t my-node-app .

### 2. Run Docker Container

    docker run -p 3000:3000 my-node-app


Visit http://localhost:3000 to see the application running.

---

## Push Docker Image to AWS ECR
### 1. Create Private Repository
    aws ecr create-repository --repository-name my-node-app --region us-east-1

### 2. Authenticate Docker to ECR
    aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com

### 3. Tag Docker Image
    docker tag my-node-app:latest <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com/my-node-app:latest

### 4. Push Docker Image
    docker push <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com/my-node-app:latest

## References

    Docker Official Documentation
    Amazon ECR Documentation

## Optional Enhancements

- Add a .dockerignore file to reduce image size
- Implement CI/CD pipelines to automatically build and push Docker images
- Include version or build status badges in README for professionalism
---
## Author: 
Onyekaozuru Tochukwu David

February 2026
