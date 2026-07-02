# ☁️ Cloud-Native Highly Available Web Application on AWS

A cloud-native project demonstrating how to deploy a highly available web application using **Amazon EC2** and **Amazon Elastic File System (EFS)**. The project uses shared storage to host a centralized Apache website that can be accessed from multiple EC2 instances.

---

## 📖 Project Overview

This project showcases the implementation of a shared storage architecture on AWS using **Amazon Elastic File System (EFS)**. Two EC2 instances are configured as Apache web servers and mounted to the same EFS file system, ensuring both servers serve identical website content.

---

## 🚀 Features

- Deploy multiple Amazon EC2 instances
- Configure Apache HTTP Server
- Create and mount Amazon EFS
- Shared website storage across servers
- Secure networking using VPC and Security Groups
- Linux-based server administration
- Highly available web hosting architecture

---

## ☁️ AWS Services Used

- Amazon EC2
- Amazon EFS
- Amazon VPC
- Security Groups
- Amazon Linux 2023
- Apache HTTP Server (httpd)

---

## 🏗️ Architecture

```
                     Internet
                         │
                  Public IP Address
                         │
        ┌────────────────┴────────────────┐
        │                                 │
+-------------------+          +-------------------+
|   EC2 Web Server1 |          |   EC2 Web Server2 |
|   Apache HTTPD    |          |   Apache HTTPD    |
+---------+---------+          +---------+---------+
          \                            /
           \                          /
            \                        /
             +----------------------+
             |      Amazon EFS      |
             |  Shared File System  |
             +----------------------+
```

---

## ⚙️ Implementation Steps

### 1. Launch EC2 Instances

- Launch two Amazon Linux EC2 instances.
- Configure Security Groups to allow SSH (22), HTTP (80), and NFS (2049).

### 2. Install Apache

```bash
sudo yum install httpd -y
sudo systemctl enable httpd
sudo systemctl start httpd
```

### 3. Create Amazon EFS

- Create an EFS file system.
- Configure Mount Targets in the VPC.

### 4. Install Amazon EFS Utilities

```bash
sudo yum install amazon-efs-utils -y
```

### 5. Mount EFS

```bash
sudo mount -t efs -o tls fs-xxxxxxxx:/ /var/www/html
```

### 6. Create Website

```bash
cd /var/www/html
sudo vi index.html
```

### 7. Verify

Open the Public IP address of either EC2 instance in your browser.

Both servers display the same website because the content is stored in Amazon EFS.

---

## 📷 Project Screenshots

### Web Server 1

![Web Server 1](server1-terminal.png)

---

### Web Server 2

![Web Server 2](server2-terminal.png)

---

### Website Output (Server 1)

![Website Output 1](website-output1.png)

---

### Website Output (Server 2)

![Website Output 2](website-output2.png)

---

## 📂 Repository Structure

```
Cloud-Native-Highly-Available-Web-Application-on-AWS/
│
├── README.md
├── index.html
├── server1-terminal.png
├── server2-terminal.png
├── website-output1.png
└── website-output2.png
```

---

## 💡 Skills Demonstrated

- AWS Cloud Computing
- Amazon EC2
- Amazon EFS
- Amazon VPC
- Linux Administration
- Apache HTTP Server
- Shared Storage
- Cloud Infrastructure
- High Availability

---

## 📚 Learning Outcomes

- Created and configured Amazon EFS.
- Mounted EFS on multiple EC2 instances.
- Hosted a centralized Apache website.
- Verified shared storage functionality.
- Improved Linux and AWS administration skills.

---

## 🔮 Future Enhancements

- Application Load Balancer (ALB)
- Auto Scaling Group
- Amazon CloudWatch Monitoring
- Route 53 DNS Integration
- HTTPS using AWS Certificate Manager
- CI/CD Pipeline with Jenkins or GitHub Actions

---

## 👨‍💻 Author

**Dineshkumar R**

**Aspiring AWS Cloud & DevOps Engineer**

- https://github.com/dineshkumarrp22-ops
- www.linkedin.com/in/dinesh-kumar-engr

---

⭐ If you found this project useful, consider giving it a **Star** on GitHub.
