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