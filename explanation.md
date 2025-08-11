# Yolo - Full Stack MERN Application

A production-ready MERN (MongoDB, Express, React, Node.js) application with Docker containerization and Ansible automation.

## 📌 Table of Contents
- [Features](#-features)
- [AWS Instance Creation & Workflow](#-aws-instance-creation--workflow)
- [Prerequisites](#-prerequisites)
- [Project Structure](#-project-structure)
- [Docker Setup](#-docker-setup)
- [Ansible Deployment](#-ansible-deployment)
- [Local Development](#-local-development)
- [Environment Variables](#-environment-variables)
- [Deployment](#-deployment)
- [Documentation](#-documentation)

## 🌟 Features
- Containerized microservices architecture
- MongoDB with persistent storage
- React 18 with optimized production build
- Node.js backend with Express
- Docker Compose for development/production
- Ansible automation for deployment
- Health checks and monitoring

## 🖼️ AWS Instance Creation & Workflow

This diagram illustrates the setup and deployment flow when provisioning and running the YOLO application on AWS using Vagrant and Ansible:

![AWS Instance Flow](aws-instance-flow.png)

## 🛠 Prerequisites

| Requirement       | Version   | Installation Guide                     |
|-------------------|-----------|----------------------------------------|
| Docker            | 20.10+    | [Docker Install](https://docs.docker.com/get-docker/) |
| Docker Compose    | 1.29+     | [Compose Install](https://docs.docker.com/compose/install/) |
| Ansible           | 2.12+     | `pip install ansible`                  |
| Vagrant           | 2.3+      | [Vagrant Install](https://www.vagrantup.com/downloads) |
| Node.js           | 16.x      | `nvm install 16`                       |

## 📁 Project Structure

yolo/
├── ansible/
│ ├── playbook.yml
│ └── roles/
│ ├── backend-deployment/
│ ├── frontend-deployment/
│ └── setup-mongodb/
├── client/
│ ├── public/
│ ├── src/
│ ├── build/
│ ├── node_modules/
│ ├── .gitignore
│ ├── Dockerfile
│ ├── package-lock.json
│ └── package.json
├── kubernetes/
│ ├── backend-deployment.yaml
│ ├── backend-service.yaml
│ ├── db-pvc.yaml
│ ├── db-service.yaml
│ ├── db-statefulset.yaml
│ ├── frontend-deployment.yaml
│ ├── frontend-service.yaml
│ ├── ingress.yaml
│ └── namespace.yaml
├── backend/
│ ├── models/
│ ├── routes/
│ ├── Dockerfile
│ ├── .gitignore
│ ├── package-lock.json
│ ├── server.js
│ ├── upload.js
│ └── package.json
├── docker-compose.yaml
├── Vagrantfile
├── explanation.md
├── node_modules/
├── roles/
│ ├── backend-deployment/
│ ├── frontend-deployment/
│ ├── setup-mongodb/
├── docker-compose.yaml
├── Vagrantfile
├── main.tf
├── playbook.yml
├── explanation.md


## 🐳 Docker Setup

- Build and run containers locally:
```bash
docker-compose up --build
```
- Backend runs on localhost:5000,Frontend on localhost:3000.

## 🤖  Ansible Deployment

### Ansible Instrumentation

- Vagrant VM provisioning with Ubuntu 20.04
- Ansible playbook with roles for:
   Backend deployment (Node.js/Express)
   Frontend deployment (React)
   MongoDB setup
- Variables files for environment configuration
- GitHub repository cloning and setup
- Containerized application deployment
- Product persistence verification

 To run Ansible:
   ansible-playbook playbook.yml -K

## 💻 Local Development
### Start backend:
 cd backend && npm install && npm run dev

### Start frontend:
 cd client && npm install && npm start

## 🔐 Environment Variables
- Make sure to configure the following .env files:
   backend/.env
   ini
   PORT=5000
   MONGO_URI=mongodb://mongo:27017/yolo-db
   client/.env
   ini 
   REACT_APP_API_URL=http://localhost:5000

## 🚀 Deployment
You can deploy using Ansible:

Ansible: Automates container deployment on the Vagrant-managed VM.

## ☸️Minikube Deployment(Local Kubernetes)
You can run the YOLO application in Minikube for local KUbernetes testing

### Start Minikube
```bash
minikube start --memory=4096 --cpus=2
```
### Create Namespace
```bash
kubectl create namespace yolo-app
```
### Apply Kubernetes Manifests
```bash
kubectl create namespace yolo-app
```
### Enable ingress
```bash
minikube addons enable ingress
```
### Access Application
```bash
minikube service frontend-lb -n yolo-app
```

## ☁️ AWS Deployment (Kubernetes on EKS)

### Create EKS cluster
```bash
eksctl create cluster --name yolo-cluster --region us-east-1 --nodes 3
```
### Deploy Application
```bash
kubectl create namespace yolo-app
kubectl apply -f k8s/ -n yolo-app
```
### Configure Ingress with AWS Load Balancer Controller
```bash
kubectl apply -f ingress.yaml -n yolo-app
```
### Get Public URL
```bash
kubectl get ingress -n yolo-app
```
## 📚 Documentation

explanation.md includes:

Role execution order rationale

Module selection justification

Architecture decisions