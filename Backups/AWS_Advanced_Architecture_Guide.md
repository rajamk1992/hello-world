
# AWS + Docker + EC2 + EKS + CI/CD
## Advanced Architecture Guide (With Diagrams)

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

## 2. S3 (Simple Storage Service)

Object storage with very high durability.

Architecture:

            Application
                 ↓
                S3
                 ↓
           Lifecycle Policy
                 ↓
              Glacier

---

## 3. RDS (Relational Database Service)

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
              EC2 / EKS
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
                 Route53
                    ↓
                   ALB
                    ↓
                Ingress
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

---

## Kubernetes Deployment Example

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: banking-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: banking-app
  template:
    metadata:
      labels:
        app: banking-app
    spec:
      containers:
        - name: banking-container
          image: <ACCOUNT_ID>.dkr.ecr.region.amazonaws.com/banking-app:latest
          ports:
            - containerPort: 3000
```

---

Rolling Update Command:

kubectl set image deployment/banking-deployment banking-container=<new-image>

---

# Enterprise Enhancements

- Horizontal Pod Autoscaler
- Blue/Green deployment
- Readiness & Liveness probes
- AWS Load Balancer Controller
- Secrets Manager
- CloudWatch monitoring
- Multi-AZ node groups

---

END OF DOCUMENT
