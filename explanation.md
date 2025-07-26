# Yolo - Full Stack MERN Application with Docker

A production-ready MERN (MongoDB, Express, React, Node.js) application with Docker containerization and Ansible automation.

## 📌 Table of Contents
- [Features](#-features)
- [IP Deliverables](#-ip-deliverables)
- [Prerequisites](#-prerequisites)
- [Project Structure](#-project-structure)
- [Docker Setup](#-docker-setup)
- [Ansible Deployment](#-ansible-deployment)
- [Local Development](#-local-development)
- [Environment Variables](#-environment-variables)
- [Deployment](#-deployment)

## 🌟 Features
- Containerized microservices architecture
- MongoDB with persistent storage
- React 18 with optimized production build
- Node.js backend with Express
- Docker Compose for development/production
- Ansible automation for deployment
- Health checks and monitoring


### Ansible Instrumentation
- ✅ Vagrant VM provisioning with Ubuntu 20.04
- ✅ Ansible playbook with roles for:
  - Backend deployment (Node.js/Express)
  - Frontend deployment (React)
  - MongoDB setup
- ✅ Variables files for environment configuration
- ✅ GitHub repository cloning and setup
- ✅ Containerized application deployment
- ✅ Product persistence verification


### Documentation
- ✅ `explanation.md` with:
  - Role execution order rationale
  - Module selection justification
  - Architecture decisions
- ✅ Comprehensive README.md

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
├── terraform/ (optional)
│ ├── backend-deployment/
│ ├── frontend-deployment/
│ └── setup-mongodb/
├── client/
│ ├── public/
│ ├── src/
│ ├── Dockerfile
│ └── package.json
├── backend/
│ ├── controllers/
│ ├── models/
│ ├── routes/
│ ├── Dockerfile
│ └── package.json
├── docker-compose.yaml
├── Vagrantfile
├── explanation.md