# 🚀 Day 3 - S3, IAM & AWS CLI

## 📌 Overview

This repository contains my hands-on practice and learning from **Day 3 of the #7DaysOfAWS Challenge**.

The focus of this day was understanding how AWS helps secure data, manage user access, and automate cloud operations using the AWS Command Line Interface (CLI).

---

## 🎯 Objectives

- Create and secure an Amazon S3 bucket
- Install and configure AWS CLI
- Launch an EC2 instance using AWS CLI
- Configure IAM permissions for a new team member
- Understand AWS security best practices

---

## 🪣 Task 1: Secure Amazon S3 Bucket

### Steps Performed

1. Logged into AWS Management Console
2. Navigated to Amazon S3
3. Created a private S3 bucket
4. Enabled Block Public Access settings
5. Verified bucket permissions
6. Tested secure access to bucket contents

### Learning Outcome

- Learned how Amazon S3 stores objects securely
- Understood bucket permissions and access control
- Explored how public access can be restricted

---

## 💻 Task 2: Configure AWS CLI

### Configure AWS CLI

```bash
aws configure
```

Enter the following details:

```text
AWS Access Key ID
AWS Secret Access Key
Default Region Name
Default Output Format
```

### Verify Configuration

```bash
aws sts get-caller-identity
```

### Learning Outcome

- Learned how to authenticate AWS CLI
- Understood how CLI communicates with AWS services
- Verified account access using terminal commands
```

## ☁️ Task 3: Launch EC2 Instance Using AWS CLI

### Launch EC2 Instance

```bash
aws ec2 run-instances \
--image-id ami-xxxxxxxxxxxxx \
--instance-type t2.micro \
--key-name my-keypair \
--security-group-ids sg-xxxxxxxx \
--subnet-id subnet-xxxxxxxx
```

### Check Running Instances

```bash
aws ec2 describe-instances
```

### Learning Outcome

- Learned how to provision EC2 instances using CLI
- Understood automation benefits compared to manual console operations
- Practiced AWS resource management through commands

---

## 👤 Task 4: IAM Access Setup

### Scenario

A new employee named **Alex** joined the organization and required specific permissions:

- ✅ View EC2 Instances
- ✅ Create S3 Buckets
- ❌ No EC2 Modification Permissions

### Steps Performed

1. Created a new IAM User
2. Created custom IAM Policies
3. Assigned permissions:
   - EC2 ReadOnly Access
   - S3 Bucket Creation Access
4. Tested access permissions
5. Verified least-privilege access model

### Learning Outcome

- Learned IAM user management
- Understood role-based access control
- Implemented the principle of least privilege

---

## 🧠 Key Concepts Learned

### Amazon S3

Amazon S3 is an object storage service used for:

- Backup & Recovery
- Static Website Hosting
- Data Archiving
- Content Distribution

### IAM

Identity and Access Management (IAM) helps:

- Create Users
- Create Groups
- Create Roles
- Assign Permissions using Policies

### AWS CLI

AWS CLI enables:

- Infrastructure Automation
- Resource Management
- Faster Cloud Operations
- Script-Based Deployments

---

## 📷 Screenshots

Add your screenshots here:

```text
screenshots/
├── s3-bucket.png
├── aws-configure.png
├── ec2-instance.png
└── iam-policy.png
```

---

## 📚 What I Learned

- Securing cloud storage is critical
- IAM permissions should follow least-privilege principles
- AWS CLI is a powerful tool for automation
- Cloud engineers frequently use CLI for infrastructure management

---

## 🏆 Challenge Progress

- [x] Secure S3 Bucket
- [x] Configure AWS CLI
- [x] Launch EC2 Using CLI
- [x] Configure IAM Permissions

---

## 🔗 Challenge

**Day 3 of #7DaysOfAWS**

Topics Covered:

- Amazon S3
- IAM
- AWS CLI
- EC2 Automation

---

## 👩‍💻 Author

**Sri Padma Chinta**

Aspiring Cloud & DevOps Engineer ☁️🚀

### Connect with Me

- LinkedIn: https://www.linkedin.com/in/sri-padma-chintha/
- GitHub: https://github.com/sripadma-git

---

### ⭐ If you found this repository useful, don't forget to star it!