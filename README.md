# Breaking a Monolithic Node.js Application into Microservices

![AWS ECS Microservices](https://img.shields.io/badge/AWS-ECS-orange?style=for-the-badge&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Node.js](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)

## Project Overview

This guided lab demonstrates the complete process of migrating a **monolithic Node.js message board application** into a modern **microservices architecture** running on AWS.

The original monolithic application handled **users**, **threads**, and **posts** in a single service — making scaling, maintenance, and independent deployments difficult.

The final architecture consists of three independent microservices:

- **Users Service** — manages user registration, authentication, profiles
- **Threads Service** — handles thread creation, listing, and management
- **Posts Service** — manages posts within threads (CRUD operations)

Each service is containerized, independently deployable, and scalable.

## Architecture Journey
`` Monolith (single Node.js app)
↓
Containerized Monolith (Docker + ECR + ECS + ALB)
↓
Refactored into 3 Microservices:
├── Users Service     → /api/users/*
├── Threads Service   → /api/threads/*
└── Posts Service     → /api/posts/*
↓
Deployed as separate ECS Services with path-based routing via Application Load Balancer ``

## Key Technologies Used

- **Backend**: Node.js + Koa framework
- **Containerization**: Docker
- **Container Registry**: Amazon Elastic Container Registry (ECR)
- **Orchestration**: Amazon Elastic Container Service (ECS) – EC2 launch type
- **Load Balancing & Routing**: Application Load Balancer (ALB) with path-based routing
- **CLI**: AWS CLI

## Final Deployment Flow

1. Each microservice has its own **Dockerfile** and **ECR repository**
2. Images are built and pushed to ECR
3. Separate **ECS Task Definitions** created for each service
4. Three **ECS Services** running on ECS cluster (EC2 launch type)
5. Single **Application Load Balancer** with listener rules:
   - `/api/users/*` → Users Service
   - `/api/threads/*` → Threads Service
   - `/api/posts/*` → Posts Service
  
📖 **Full Guided Lab Documentation**  
https://www.notion.so/Breaking-a-Monolithic-Node-js-Application-into-Microservices-2e1e8585d3ec80499445e4dc69a30517
