# AWS Elastic Container Service (ECS)

## Overview

Amazon Elastic Container Service (ECS) is a fully managed container orchestration service that makes it easy to deploy, manage, and scale Docker containers on AWS.

With ECS, you don't have to manage the underlying infrastructure manually. AWS handles container scheduling, scaling, and monitoring.

---

# What is AWS ECS?

AWS ECS allows you to:

- Run Docker containers on AWS
- Deploy applications quickly
- Scale applications automatically
- Manage multiple containers easily
- Integrate with other AWS services

---

# Prerequisites

Before creating an ECS service, make sure you have:

- AWS Account
- Docker installed
- AWS CLI configured
- IAM permissions
- A Docker image (or sample application)

---

# Architecture

```
Docker Application
        │
        ▼
   Build Docker Image
        │
        ▼
 Push Image to Amazon ECR
        │
        ▼
 Create ECS Cluster
        │
        ▼
 Create Task Definition
        │
        ▼
 Create ECS Service
        │
        ▼
 Application Running
```

---

# Steps to Deploy an Application

## Step 1: Create a Docker Image

Build your application as a Docker image.

```bash
docker build -t my-app .
```

---

## Step 2: Push Image to Amazon ECR

1. Open AWS Console
2. Search **Elastic Container Registry (ECR)**
3. Create a repository
4. Push your Docker image to ECR

---

## Step 3: Create an ECS Cluster

1. Open AWS Console
2. Search **Elastic Container Service (ECS)**
3. Click **Create Cluster**
4. Choose **Fargate** or **EC2**
5. Give the cluster a name
6. Click **Create**

---

## Step 4: Create a Task Definition

1. Go to **Task Definitions**
2. Click **Create Task Definition**
3. Select **Fargate**
4. Enter:
   - Task Name
   - CPU
   - Memory
5. Add a container
6. Select the Docker image from Amazon ECR
7. Set the container port
8. Create the task definition

---

## Step 5: Create an ECS Service

1. Open your ECS Cluster
2. Click **Create Service**
3. Choose the task definition
4. Select the desired number of tasks
5. Configure networking
6. Attach a Load Balancer (optional)
7. Click **Create**

---

# ECS Components

## Cluster

A cluster is a logical group where your containers run.

---

## Task Definition

A blueprint that defines:

- Docker image
- CPU
- Memory
- Port mapping
- Environment variables

---

## Task

A running instance of a task definition.

---

## Service

A service keeps the desired number of tasks running automatically.

Example:

Desired Tasks = **2**

If one task stops, ECS automatically starts another one.

---

# ECS Launch Types

## Fargate

- No server management
- Fully managed by AWS
- Easy to use
- Pay only for resources used

---

## EC2

- You manage the EC2 instances
- More control
- Suitable for advanced workloads

---

# Benefits of ECS

- Fully managed
- Easy deployment
- High availability
- Auto scaling
- Load balancing support
- Secure IAM integration
- CloudWatch monitoring
- Works seamlessly with Amazon ECR

---

# AWS Services Used

- Amazon ECS
- Amazon ECR
- IAM
- CloudWatch
- Elastic Load Balancer (Optional)
- VPC
- Security Groups

---

# Workflow

```
Application
      │
      ▼
Docker Build
      │
      ▼
Amazon ECR
      │
      ▼
Task Definition
      │
      ▼
ECS Cluster
      │
      ▼
ECS Service
      │
      ▼
Running Containers
      │
      ▼
Users Access Application
```

---

# Advantages

- Easy container deployment
- Automatic scaling
- High availability
- Cost-effective
- Secure
- Fully managed
- Integrates with many AWS services

---

# Conclusion

Amazon ECS is an AWS service for running and managing Docker containers. By using ECS with Amazon ECR, you can deploy containerized applications quickly, scale them automatically, and reduce infrastructure management.

# For refrence please see the screenshot 

Author 
Mudasir Ahmad   //@anberlin
