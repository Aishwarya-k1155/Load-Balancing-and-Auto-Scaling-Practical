# Load-Balancing-and-Auto-Scaling-Practical
Task 7: AWS Load Balancing and Auto Scaling setup for a web application.
# Task 7: Load Balancing and Auto Scaling for a Web Application

## Objective
In this task, I configured Load Balancing and Auto Scaling for a simple web application hosted on AWS EC2 instances to understand how scalability and fault tolerance work in cloud computing.

---

## Tools Used
- AWS EC2  
- Elastic Load Balancer (Application Load Balancer)  
- Auto Scaling Group  
- Auto Scaling Policies (Trigger-based scaling)  
- Ubuntu Server (Free Tier)

---

## Steps Performed

### 1. Created a Basic Web App
I created a simple HTML page named `index.html` and hosted it using Apache on two EC2 instances named **WebServer1** and **WebServer2**.

### 2. Configured Security Group
I configured a security group that allowed inbound HTTP (port 80) and SSH (port 22) access to both instances.

### 3. Created Load Balancer
I created an **Application Load Balancer (ALB)** to distribute HTTP traffic across both EC2 instances.  
A **Target Group** was also configured with health checks on port 80 to ensure only healthy instances receive traffic.

### 4. Configured Auto Scaling Group
I created a **Launch Template** using the same configuration as my EC2 instances.  
Then, I set up an **Auto Scaling Group** with:  
- Minimum capacity: 1 instance  
- Desired capacity: 2 instances  
- Maximum capacity: 3 instances  
I defined a **scaling policy** (trigger) that automatically launches or terminates instances based on utilization thresholds.

### 5. Verified Setup
I accessed the Load Balancer DNS name and verified that the web page was served successfully from both instances.  
I also checked the **Auto Scaling Activity History** to confirm that new instances were launched automatically when scaling conditions were met.

---

## Screenshots
Included:  
1. EC2 Instances (Running)  
2. Load Balancer (Active)  
3. Target Group (Healthy)  
4. Auto Scaling Group configuration  
5. Auto Scaling Activity History  
6. Web page output via Load Balancer DNS name

---

## Outcome
By completing this task, I gained hands-on experience with AWS Load Balancing and Auto Scaling.  
I learned how these services ensure **high availability**, maintain **application performance**, and optimize **cost efficiency** by automatically managing instance capacity.

---

## Commands Used

```bash
# Update packages
sudo apt update

# Install Apache web server
sudo apt install apache2 -y

# Enable and start Apache
sudo systemctl enable apache2
sudo systemctl start apache2

# Open index.html file for editing
sudo nano /var/www/html/index.html
index.html
html
Copy code
<!DOCTYPE html>
<html>
<head>
  <title>Cloud Auto Scaling Demo</title>
</head>
<body>
  <h2>Hello from my Cloud Instance!</h2>
  <p>This page is served from a cloud VM behind a load balancer.</p>
</body>
</html>

Author
Aishwarya Kopulwar
Cloud and Linux Engineer Trainee
kopulwaraishwarya88@gmail.com
