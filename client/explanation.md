# Yolo - Full Stack MERN Application with Docker

![MERN Stack](https://miro.medium.com/max/1200/1*H4PL7crbD3iDxUkXCCgXyw.png)

A production-ready MERN (MongoDB, Express, React, Node.js) application with Docker containerization and CI/CD pipeline integration.

## 📌 Table of Contents
- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Project Structure](#-project-structure)
- [Docker Setup](#-docker-setup)
- [Local Development](#-local-development)
- [Environment Variables](#-environment-variables)
- [Deployment](#-deployment)
- [Troubleshooting](#-troubleshooting)
- [API Reference](#-api-reference)
- [Contributing](#-contributing)
- [License](#-license)

## 🌟 Features
- Containerized microservices architecture
- MongoDB with persistent storage
- React 18 with optimized production build
- Node.js backend with Express
- Docker Compose for development/production
- Pre-configured CI/CD pipeline example
- Health checks and monitoring

## 🛠 Prerequisites

| Requirement       | Version   | Installation Guide                     |
|-------------------|-----------|----------------------------------------|
| Docker            | 20.10+    | [Docker Install](https://docs.docker.com/get-docker/) |
| Docker Compose    | 1.29+     | [Compose Install](https://docs.docker.com/compose/install/) |
| Node.js           | 16.x      | `nvm install 16`                       |
| npm               | 8.x+      | Comes with Node.js                     |

## 📁 Project Structure
yolo/
├── client/ # React Frontend
│ ├── public/ # Static assets
│ ├── src/ # React components
│ ├── Dockerfile # Production build config
│ ├── package.json # Frontend dependencies
│ └── .env.development # Client environment vars
│
├── backend/ # Node.js API
│ ├── controllers/ # Route controllers
│ ├── models/ # MongoDB models
│ ├── routes/ # API endpoints
│ ├── Dockerfile # Backend config
│ ├── package.json # Backend dependencies
│ └── .env # Server environment vars
│
├── docker-compose.yml # Development environment
├── docker-compose.prod.yml # Production environment
├── .github/workflows/ # CI/CD pipelines
│ └── deploy.yml
└── README.md # This document

## 🐳 Docker Setup

### Container Images

| Image Name                          | Last Updated       | Status  | Description                   |
|-------------------------------------|--------------------|---------|-------------------------------|
| `elizabethkimani/yolo-app`          | 23 hours ago       | Public  | Production-ready full stack   |

### Development Environment
```bash
# Build and start all services
docker-compose up --build

# View running containers
docker-compose ps

# Access logs
docker-compose logs -f client

#Production Build
docker-compose -f docker-compose.prod.yml up --build -d

#Local Deployment
##Frontend Setup
cd client
npm install
npm start  # http://localhost:3000

##Backend Setup
cd backend
npm install
npm run dev  # http://localhost:5000

#Environmental Variables
##Backend
MONGO_URI=mongodb://mongo:27017/yolo
PORT=5000

##Frontend
REACT_APP_API_URL=http://localhost:5000
REACT_APP_ENV=development

#Deployment
##Push to dockerhub
docker build -t elizabethkimani/yolo-app .
docker push elizabethkimani/yolo-app