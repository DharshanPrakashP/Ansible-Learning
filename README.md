# 🚀 Working with Ansible - FastAPI Deployment with Ansible — Day 1
[![My Skills](https://skillicons.dev/icons?i=ansible,linux,py&theme=dark)](https://skillicons.dev)


This repository documents the Day 1 progress of automating a FastAPI application deployment using **Ansible** on a local machine via **WSL (Ubuntu 24.04)**.

# ✅ Project Purpose / Use Case
> ⚙️ This project demonstrates how to use Ansible to automate local FastAPI deployments — a foundational step in DevOps workflows. It serves as the base for future EC2 or CI/CD integrations.

## 📦 Project Overview

This playbook performs the following tasks:

- Installs Python3 and pip
- Creates a virtual environment
- Installs FastAPI and Uvicorn from `requirements.txt`
- Starts the FastAPI app on port `8000` using `uvicorn`

## 📁 Folder Structure
    .
    ├── fast-api/
    │   ├── venv/                  # Virtual environment (ignored by git)
    │   ├── main.py                # FastAPI application
    │   └── requirements.txt       # Python dependencies
    ├── .gitignore                 # Git ignore rules (venv, logs, pycache)
    ├── fastapi-deploy.yml         # Main Ansible playbook for deployment
    ├── inventory.ini              # Ansible inventory (localhost setup)
    └── playbook.yml               # (Optional/legacy playbook)
    

# 📦 Pre-requisites
## 🖥️ System Requirements

- **Ubuntu** (WSL or native)
- **Python** 3.8+
- **Ansible** 2.10+
- **Git**
---

## 📥 Install Required Packages

Run the following commands to set up your environment:

``` 
# Update package list
sudo apt update

# Install Python and pip
sudo apt install -y python3 python3-pip python3-venv

# Install Ansible
sudo apt install -y ansible
```

# 🚀 How to Use


## 1️⃣ Clone the Repository

```bash
git clone https://github.com/DharshanPrakashP/Ansible-Learning.git
cd Ansible-Learning

```

## 2️⃣ Run the Ansible Playbook

Execute the playbook with local inventory:
```
ansible-playbook -i inventory.ini fastapi-deploy.yml --ask-become-pass
```
🔐 You’ll be prompted for your sudo password during execution.

## 3️⃣ Verify the FastAPI App is Running

Once the playbook completes, check if the server is live:
```
curl <http://127.0.0.1:8000>
```

You should see:
```
{"message": "Hello, World!"}
```

---

## ✅ What's Next?

This repo is part of a larger DevOps journey:

- [ ] Add SSH-based EC2 deployment
- [ ] Pull updated Docker images with Ansible
- [ ] Integrate GitHub Webhooks or CI pipelines
- [ ] Use Ansible Roles for modular playbooks

> Stay tuned for Day 2 🚀
