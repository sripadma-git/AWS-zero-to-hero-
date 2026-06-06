# 🚀 Day 4 – Databases, Lambda & Automation | 7 Days of AWS Challenge

## 📖 Overview

Day 4 of the **7 Days of AWS Challenge** focused on databases, serverless computing, and automation. The objective was to understand how modern cloud applications store data, scale efficiently, and automate infrastructure management using AWS services.

---

## 🧠 Concepts Covered

### 💾 Amazon RDS

Amazon Relational Database Service (RDS) is a fully managed relational database service that simplifies database administration by handling backups, patching, monitoring, and scaling.

#### Key Benefits
- Managed MySQL database
- Automated backups
- High availability
- Easy scalability
- Improved security

---

### ⚡ Amazon DynamoDB

Amazon DynamoDB is a fully managed NoSQL database that delivers single-digit millisecond performance at any scale.

#### Key Benefits
- Serverless architecture
- High availability
- Flexible schema
- Automatic scaling
- Low-latency performance

---

### 🌀 AWS Lambda

AWS Lambda allows developers to run code without provisioning or managing servers.

#### Key Benefits
- Pay only for execution time
- Event-driven architecture
- Automatic scaling
- Seamless integration with AWS services

---

# 🎯 Tasks Completed

## ✅ Task 1: Learn & Share

Studied:

- Amazon RDS
- Amazon DynamoDB
- AWS Lambda

Created and shared a LinkedIn post summarizing the concepts and real-world use cases.

---

## ✅ Task 2: Database Migration to Amazon RDS

### Scenario

Migrated a self-managed MySQL database to Amazon RDS to improve scalability and reduce operational overhead.

### Activities Performed

- Created a MySQL RDS instance
- Configured database settings
- Established secure connectivity between EC2 and RDS
- Tested database connectivity
- Performed CRUD operations

### Architecture

```text
EC2 Instance
     │
     ▼
Amazon RDS (MySQL)
```

---

## ✅ Task 3: Deploy a Two-Tier Flask Application

### Project Components

- Flask Web Application
- Amazon EC2
- Amazon RDS (MySQL)
- Docker
- Docker Compose

### Workflow

```text
User
  │
  ▼
Flask Application (Docker Container)
  │
  ▼
Amazon RDS MySQL
```

### Deployment Steps

1. Launched EC2 Instance
2. Installed Docker & Docker Compose
3. Created Amazon RDS MySQL Database
4. Configured Security Groups
5. Connected Flask Application to RDS
6. Deployed Flask Application using Docker
7. Verified CRUD Operations

---

## 🔄 Future Scaling Architecture

```text
Users
  │
  ▼
Application Load Balancer
  │
  ▼
Auto Scaling Group
  │
 ├── EC2 Instance 1
 ├── EC2 Instance 2
 └── EC2 Instance N
  │
  ▼
Amazon RDS
```

---

## ✅ Task 4: EC2 Start/Stop Automation Using Lambda

### Scenario

To optimize cloud costs, EC2 instances were automated to start and stop based on schedules.

### Services Used

- AWS Lambda
- Amazon EventBridge
- Python Boto3

### Workflow

```text
EventBridge Schedule
        │
        ▼
AWS Lambda Function
        │
        ▼
Start / Stop EC2 Instances
```

### Benefits

- Reduced infrastructure costs
- Automated resource management
- No manual intervention required

---

# 🛠️ AWS Services Used

- Amazon EC2
- Amazon RDS
- Amazon DynamoDB
- AWS Lambda
- Amazon EventBridge
- IAM
- VPC
- Security Groups
- Docker
- Docker Compose

---

# 📚 Key Learnings

- Difference between SQL and NoSQL databases
- Database migration to Amazon RDS
- Secure networking between EC2 and RDS
- Containerized application deployment using Docker
- Serverless automation using AWS Lambda
- Cost optimization using scheduled automation
- Real-world cloud architecture design

---

# 🎓 Challenge Outcome

Successfully explored database management, serverless computing, and infrastructure automation while deploying a cloud-native two-tier application using AWS services.

---
