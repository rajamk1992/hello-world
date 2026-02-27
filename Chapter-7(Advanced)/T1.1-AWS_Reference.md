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

# PART 2: Docker + Node Application with EC2

## Step 1: Sample Node App (app.js)

``` javascript
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Docker running on EC2 🚀");
});

app.listen(3000, "0.0.0.0", () => {
  console.log("Server started");
});
```

## Step 2: Dockerfile

``` dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY . .
EXPOSE 3000
CMD ["node", "app.js"]
```

## Step 3: Build Docker Image

    docker build -t banking-app .

## Step 4: Run Container

    docker run -d -p 80:3000 --restart always --name banking-container banking-app

Access: http://EC2-PUBLIC-IP

------------------------------------------------------------------------

# PART 3: Advanced Level -- CI/CD Pipeline with EKS

Architecture Flow:

Developer Push → Build Docker Image → Push to ECR → Deploy to EKS →
Rolling Update

## 1. Build and Push to ECR

    docker build -t banking-app .
    docker tag banking-app:latest <ACCOUNT_ID>.dkr.ecr.region.amazonaws.com/banking-app:latest
    docker push <ACCOUNT_ID>.dkr.ecr.region.amazonaws.com/banking-app:latest

## 2. Kubernetes Deployment (deployment.yaml)

``` yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: banking-deployment
spec:
  replicas: 2
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

Apply:

    kubectl apply -f deployment.yaml

## 3. Service (service.yaml)

``` yaml
apiVersion: v1
kind: Service
metadata:
  name: banking-service
spec:
  type: LoadBalancer
  selector:
    app: banking-app
  ports:
    - port: 80
      targetPort: 3000
```

Apply:

    kubectl apply -f service.yaml

# Summary

AWS Core Services → Infrastructure foundation\
Docker + EC2 → Simple container deployment\
CI/CD + EKS → Scalable, production-ready container orchestration
