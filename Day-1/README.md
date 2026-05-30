# ☁️ Day 1: Introduction to Cloud & AWS Basics

Welcome to Day 1 of the **7 Days of AWS Challenge**! This repository contains my structured notes, key takeaways, and service models explored today.

---

## 1. AWS Pricing Models 💰

AWS provides flexible pricing structures tailored to different application workloads. 

*   **Pay-as-you-go (On-Demand):** Pay for compute or storage capacity by the second or hour. No long-term commitments or upfront payments.
*   **Reserved Instances (RIs) / Savings Plans:** Commit to a consistent usage amount (1 or 3-year term) in exchange for a massive discount (up to 72%) compared to On-Demand pricing.
*   **Spot Instances:** Spare AWS compute capacity available at steep discounts (up to 90%). However, AWS can reclaim these instances with a 2-minute warning.

### 💡 Recommendation for Startups & Learners
*   **For Learners:** **Pay-as-you-go (coupled with the AWS Free Tier)** is the best choice. It allows you to experiment with services for pennies and shut them down when finished without any lingering commitments.
*   **For Startups:** A hybrid strategy works best. Start with **Pay-as-you-go** to test product-market fit. Once baseline traffic becomes predictable, transition core workloads to **Savings Plans** to slash costs while keeping **Spot Instances** for background data processing or testing environments.

---

## 2. Comparing Cloud Models 🏛️

| Model | Description | Best Suited For |
| :--- | :--- | :--- |
| **On-Premises (Private)** | All infrastructure is owned, hosted, and maintained physically by the organization within their own data centers. | **Government projects, large banks**, or highly regulated industries requiring total physical control over data. |
| **Cloud (Public)** | All infrastructure is owned and managed by a third-party provider (like AWS) and accessed securely over the internet. | **Startups, fast-growing tech companies**, and businesses looking to eliminate hardware maintenance and scale instantly. |
| **Hybrid** | A combination of on-premises infrastructure and public cloud, connected securely to allow data and apps to be shared between them. | **Large Enterprises** undergoing a gradual migration to the cloud, or businesses needing to keep legacy databases local while utilizing cloud scaling for applications. |

---

## 3. Cloud Service Models (IaaS, PaaS, SaaS) ⚙️

The service models define the level of control and management you have over your infrastructure.

### Infrastructure as a Service (IaaS)
You rent the raw hardware (servers, storage, networking). You are responsible for managing the operating system, middleware, and applications.
*   **Generic Examples:** DigitalOcean, Linode.
*   **AWS Equivalent:** `AWS EC2 (Elastic Compute Cloud)` – Provides virtual servers where you choose the OS and install everything from scratch.

### Platform as a Service (PaaS)
The cloud provider manages the underlying hardware and operating systems. You only focus on deploying and managing your application code.
*   **Generic Examples:** Heroku, Google App Engine.
*   **AWS Equivalent:** `AWS Lambda` (Serverless execution where you just upload code) or `AWS Elastic Beanstalk` (just drop your code, and AWS handles provisioning and load balancing).

### Software as a Service (SaaS)
A complete, fully managed software product that you access over the internet, typically via a web browser.
*   **Generic Examples:** Gmail, Microsoft 365, Salesforce.
*   **AWS Equivalent:** `Amazon WorkMail` (managed business email) or `Amazon Chime` (video conferencing).

---

## 4. AWS History & Key Milestones ⏳

AWS didn't just build a cloud platform; it essentially created the modern cloud industry.

*   **2002:** Amazon internally realized they were excellent at building scalable infrastructure and decided to productize it as a standardized platform.
*   **2006:** **Official Launch of AWS.** It disrupted the industry by launching **Amazon S3** (Simple Storage Service) followed tightly by **Amazon EC2** in the same year, allowing anyone with a credit card to rent virtual computer power.
*   **2014:** Launched **AWS Lambda**, pioneering the "Serverless" revolution where users don't even have to look at or configure a server.
*   **Present:** AWS remains the global #1 cloud provider, holding roughly a third of the entire cloud infrastructure market share due to its massive first-mover advantage, immense global data center footprint, and relentless pace of service innovation.

---

### 🚀 Connect with Me!
*   **Challenge Organizer:** [@TrainWithShubham](https://github.com/LondheShubham153)
*   **Hashtags:** #7DaysOfAWS #AWSwithTWS
