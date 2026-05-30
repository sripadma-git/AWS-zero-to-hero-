# 🔒 Day 2: AWS WAF (Web Application Firewall)

Welcome to Day 2 of the **7 Days of AWS Challenge**! Today's focus is on web application security, understanding how AWS WAF works, and deploying it to protect infrastructure from common exploits.

---

## 🧠 What is AWS WAF?

**AWS WAF** is a web application firewall that protects web applications and APIs against common web exploits and bots that can compromise security, affect availability, or consume excessive resources. It operates at **Layer 7 (Application Layer)** of the OSI model.

### Key Concepts
*   **Web ACL (Access Control List):** The core container that shields your resources. It aggregates the rules you define to inspect incoming traffic.
*   **Rules & Actions:** Individual criteria evaluated against incoming HTTP(S) requests. When a rule matches, WAF executes one of three actions:
    *   `Allow`: Forwards the request to the application.
    *   `Block`: Drops the request instantly, returning an **HTTP 403 Forbidden** error.
    *   `Count`: Logs the match for monitoring/testing without interfering with the traffic flow.
*   **Managed Rule Groups:** Pre-packaged sets of rules written and maintained by AWS or security partners (e.g., protections against the OWASP Top 10 vulnerabilities).

### Common Threats Mitigated
*   **SQL Injection (SQLi):** Malicious SQL code injections targeting database layers.
*   **Cross-Site Scripting (XSS):** Malicious script injections intended to execute in users' browsers.
*   **Rate Limiting:** Automatic blocking of IP addresses that exceed a safe request threshold over a rolling 5-minute period (essential for DDoS protection).

---

## 🛠️ Hands-On Project: Web App Protection

### Step 1: Set Up the Web Application
1. Navigate to the **EC2 Console** and click **Launch Instance**.
2. Pick an **Amazon Linux 2 AMI** and use the Free Tier eligible `t2.micro` instance type.
3. Under **Network Settings**, check the box to **Allow HTTP traffic from the internet**.
4. Scroll down to **Advanced Details** ➡️ **User Data**, and paste the bootstrap script:
```bash
   #!/bin/bash
   yum update -y
   yum install -y httpd
   systemctl start httpd
   systemctl enable httpd
   echo "<h1>My Secure Web App - Day 2 AWS Challenge</h1>" > /var/www/html/index.html
```

5. Launch the instance and verify accessibility by navigating to its Public IP in your browser.

### Step 2: Configure the AWS WAF Web 

1. Navigate to the WAF & Shield console.

2. Go to Web ACLs and select Create web ACL.

3. Fill in the basic details:

- Name: Day2-Web-ACL

- Resource type: Regional resources

4. Advance to Add rules and rule groups:

- Click Add rules ➡️ Add managed rule groups.

- Expand AWS managed rule groups and enable Core rule set (CRS) and SQL database.

5. Keep the default web ACL action set to Allow and finish creating the ACL.


### Step 3: Attach WAF to the Architecture.

Note: AWS WAF cannot be attached directly to a standalone EC2 instance. It must protect an Application Load Balancer (ALB), Amazon CloudFront distribution, or an API Gateway.

1. Navigate to EC2 ➡️ Load Balancers and create an Application Load Balancer pointing to your EC2 target group on Port 80.

2. Return to the AWS WAF Console ➡️ select Day2-Web-ACL ➡️ navigate to the Associated AWS resources tab.

3. Click Add AWS resources, select Application Load Balancer, check your newly provisioned ALB, and click Add.

### Step 4: Test the Defensive Rules

1. Copy your ALB's DNS name and paste it into your browser to ensure normal traffic is allowed.

2. Simulate a basic malicious SQL injection attempt by appending an exploit string to your URL query parameter: 
- http://<YOUR-ALB-DNS-NAME>/?id=1' OR '1'='1

3. Verify that AWS WAF immediately blocks the request and surfaces an HTTP 403 Forbidden page.