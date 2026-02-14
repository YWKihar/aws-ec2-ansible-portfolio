# AWS EC2 Ansible Portfolio Deployment 🚀

Production-style Ansible project for automated deployment of a static portfolio website on **AWS EC2 (Ubuntu)**.

This repository demonstrates full-stack infrastructure automation including:

- EC2 provisioning readiness
- Apache installation and configuration
- Static website deployment
- Secure inventory handling
- Infrastructure as Code (IaC) principles

---

## 📌 Project Overview

This project automates the deployment of a static portfolio website to an AWS EC2 instance using Ansible.

The playbook performs:

- Apache installation
- Apache service configuration
- Deployment of website files
- Service enablement on system boot
- Secure SSH-based automation

---

## 🧱 Infrastructure Context

| Component        | Details                         |
|------------------|---------------------------------|
| Cloud Provider   | AWS                             |
| Compute          | EC2 (Ubuntu)                    |
| Web Server       | Apache2                         |
| Automation Tool  | Ansible                         |
| Access Method    | SSH (.pem key)                  |
| Deployment Type  | Static Website                  |

---

## 📂 Repository Structure

```
aws-ec2-ansible-portfolio/
│
├── portfolio/                # Static website files
│   ├── index.html
│   ├── style.css
│   ├── script.js
│   └── assets/
│
├── deploy_portfolio.yml      # Main Ansible playbook
├── inventory.example.ini     # Example inventory file
├── .gitignore                # Protects private keys and real inventory
└── README.md
```

---

## 🔐 Security Best Practices

Sensitive files are intentionally excluded:

- `inventory.ini` is ignored
- SSH private keys are ignored
- No public IP addresses are stored in the repository

You must create your own secure inventory file locally.

---

## ⚙️ Prerequisites

Before running the playbook, ensure:

- Ansible installed on your control node
- AWS EC2 Ubuntu instance running
- Port 80 allowed in Security Group
- SSH key (.pem file)

---

## 📝 Step 1 — Clone Repository

```bash
git clone https://github.com/YWKihar/aws-ec2-ansible-portfolio.git
cd aws-ec2-ansible-portfolio
```

---

## 📝 Step 2 — Configure Inventory

Create a file named:

```
inventory.ini
```

Example structure:

```ini
[webservers]
YOUR_EC2_PUBLIC_IP

[webservers:vars]
ansible_user=ubuntu
ansible_ssh_private_key_file=YOUR_SSH_KEY
```

---

## 📝 Step 3 — Secure SSH Key

```bash
chmod 400 YOUR_SSH_KEY
```

---

## 🚀 Step 4 — Deploy Portfolio Website

```bash
ansible-playbook -i inventory.ini deploy_portfolio.yml
```

---

## ✅ Expected Outcome

After successful execution:

- Apache is installed
- Apache service is running
- Website files are deployed to `/var/www/html`
- Portfolio accessible via:

```
http://YOUR_EC2_PUBLIC_IP
```

---

## 🧠 What This Project Demonstrates

This repository proves understanding of:

- Infrastructure as Code (IaC)
- Cloud automation with AWS
- Ansible configuration management
- Secure inventory practices
- Production-ready deployment structure
- Real-world DevOps workflow

---

## 📈 Possible Future Enhancements

- Convert to Ansible Roles
- Add HTTPS using Let's Encrypt
- Add CI/CD using GitHub Actions
- Dockerize the portfolio
- Terraform-based EC2 provisioning

---

## 👤 Maintainer

**Yousef Kihar**  
DevOps Engineer | Cloud Automation | Infrastructure as Code  

GitHub: https://github.com/YWKihar
