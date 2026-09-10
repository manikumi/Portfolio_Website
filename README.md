# 🚀 AWS End-to-End Web Application Deployment

This repository contains the deployment configurations, scripts, and documentation for hosting a scalable, secure, and production-ready portfolio web application on AWS.

---

## 🔗 Project Links

- 📝 **Medium Article:** [AWS Project (End-To-End Web Application Deployment)](https://medium.com/@saimanishkumar11/aws-project-end-to-end-web-application-deployment-842d3ad0a2c1)
- 💼 **LinkedIn Post:** [DevOps & AWS Deployment Showcase](https://www.linkedin.com/posts/manish-kumar-s98_aws-devops-deployment-activity-7182786641953013760-biXd)

---

## 📌 Project Overview

The goal of this project is to build and deploy a web application leveraging core AWS networking and compute services. It covers everything from setting up a custom VPC topology to provisioning web servers and deploying application assets.

---

## 🛠 Step-by-Step Deployment Guide

### Phase 1: Custom VPC & Network Infrastructure
1. **Create Custom VPC:** Provisioned a Virtual Private Cloud (VPC) with IPv4 CIDR block (`10.0.0.0/16`).
2. **Configure Subnets:**
   - Created **Public Subnets** for public-facing assets and **Private Subnets** for secure internal isolation.
   - Enabled **Auto-Assign Public IPv4 Address** on the Public Subnet settings.
3. **Set Up Internet Gateway & Route Tables:**
   - Provisioned an **Internet Gateway (IGW)** and attached it to the VPC.
   - Configured a **Public Route Table**, associated it with the Public Subnet, and added an outbound route (`0.0.0.0/0`) targeting the IGW.

---

### Phase 2: Server Provisioning & Configuration
1. **Launch EC2 Instance:**
   - Provisioned an EC2 instance within the custom Public Subnet.
   - Configured Security Groups to allow inbound traffic on **Port 80 (HTTP)** and **Port 22 (SSH)**.
2. **Connect via SSH:**
   - Established a secure SSH session to the server using **MobaXterm**.
   - Updated system packages:
     ```bash
     sudo apt update -y
     ```

---

### Phase 3: Web Server & Portfolio Application Deployment
1. **Install & Configure Apache2:**
   - Installed and enabled the web server:
     ```bash
     sudo apt install apache2 -y
     sudo systemctl start apache2
     sudo systemctl enable apache2
     ```
   - Verified installation by hitting the server's **Public IP** via browser.

2. **Deploy Application Code:**
   - Installed Git and cloned the portfolio web app repository:
     ```bash
     sudo apt install git -y
     git clone <REPOSITORY_URL>
     ```
   - Deployed web assets by copying source files directly into Apache's default web directory (`/var/www/html/`).
   - Verified web application availability live on the public IP.

---

## 👨‍💻 Author

**Manish Kumar S**
- 💼 **LinkedIn:** [Manish Kumar S](https://linkedin.com/in/manish-kumar-s98)
- 📝 **Medium:** [@saimanishkumar11](https://medium.com/@saimanishkumar11)
- 📧 **Email:** saimanishkumar11@gmail.com
