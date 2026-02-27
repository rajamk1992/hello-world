# AWS + Docker + EKS Complete Guide

------------------------------------------------------------------------

# PART 1: Most Commonly Used AWS Services

## 1. EC2 (Elastic Compute Cloud)

-   Virtual servers in the cloud
-   Used to host applications
-   Full control over OS and environment
-   Suitable for traditional and containerized applications

## 2. S3 (Simple Storage Service)

-   Object storage service
-   Used for file storage (images, PDFs, backups)
-   Highly durable and scalable
-   Common in banking for document storage and logs

## 3. RDS (Relational Database Service)

-   Managed SQL database (MySQL, PostgreSQL, etc.)
-   Automated backups
-   Multi-AZ for high availability
-   No manual database server management

## 4. IAM (Identity and Access Management)

-   Manages users and permissions
-   Controls access to AWS resources
-   Essential for secure production systems

## 5. CloudWatch

-   Monitoring and logging service
-   Tracks CPU, memory, logs
-   Used for alerts and alarms

## 6. VPC (Virtual Private Cloud)

-   Private network inside AWS
-   Controls subnets, routing, internet access
-   Critical for secure architecture

## 7. ECR (Elastic Container Registry)

-   Stores Docker images securely
-   Integrated with ECS and EKS

## 8. EKS (Elastic Kubernetes Service)

-   Managed Kubernetes service
-   Used for container orchestration
-   Supports auto scaling and rolling deployments

------------------------------------------------------------------------

# AWS + Docker + EC2 
---
# PART 1: Most Commonly Used AWS Services (Detailed)

## 1. EC2 (Elastic Compute Cloud)
Virtual servers in AWS cloud.

Use Cases:
- Hosting backend applications
- Running Docker containers
- Legacy systems
- Batch processing

Architecture:

                Users
                  ↓
            Load Balancer
                  ↓
                 EC2
                  ↓
                 RDS

---


## 2. RDS (Relational Database Service)

Managed SQL database with Multi-AZ support.

Architecture:

            App Server
               ↓
          RDS Primary
               ↓
          RDS Standby

---

## 4. IAM
Controls authentication and authorization.

---

## 5. VPC (Virtual Private Cloud)

Production Network Layout:

                Internet
                   ↓
             Internet Gateway
                   ↓
            Public Subnet
                   ↓
             Load Balancer
                   ↓
            Private Subnet
                   ↓
                  EC2
                   ↓
                  RDS

---

# PART 2: Docker + Node Application with EC2

## Architecture

                User
                  ↓
            Public IP
                  ↓
                EC2
                  ↓
              Docker
                  ↓
             Node App
                  ↓
                 RDS

---

## Node Application

```javascript
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Docker running on EC2 🚀");
});

app.listen(3000, "0.0.0.0", () => {
  console.log("Server started");
});
```

---

## Dockerfile

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY . .
EXPOSE 3000
CMD ["node", "app.js"]
```

---
docker build -t banking-app .

Run Container:

docker run -d -p 80:3000 --restart always --name banking-container banking-app

---

# PART 3: Advanced – CI/CD Pipeline with EKS

## High-Level CI/CD Architecture

        Developer Push
                ↓
            CI Build
                ↓
        Docker Image Build
                ↓
               ECR
                ↓
             EKS Cluster
                ↓
           Kubernetes Pods
                ↓
            Load Balancer
                ↓
               Users

---

## EKS Production Architecture

                  Users
                    ↓
                 Route
                    ↓
               EKS Cluster
                    ↓
          ┌───────────────┐
          │  Pod 1        │
          │  Pod 2        │
          │  Pod 3        │
          └───────────────┘
                    ↓
                   RDS
                    ↓
                    S3