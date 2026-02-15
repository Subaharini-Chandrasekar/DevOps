# 🚀 Ansible Configuration Management Project

![Ansible](https://img.shields.io/badge/Ansible-2.x-EE0000?style=for-the-badge&logo=ansible)
![Platform](https://img.shields.io/badge/Platform-Linux-2CA5E0?style=for-the-badge&logo=linux)
![Automation](https://img.shields.io/badge/Automation-Configuration%20Management-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

---

# 📌 What is Ansible?

Ansible is an open-source **IT automation and configuration management tool** developed by Red Hat.

It helps automate:

- 🖥️ Server configuration  
- 📦 Application deployment  
- 🔄 Software updates  
- 🛠️ Infrastructure provisioning  
- 🔐 Security compliance  

Ansible uses **YAML-based Playbooks** and works over **SSH (agentless architecture)**.

---

# 🏗️ Why Use Ansible?

✅ Agentless (No installation on client nodes)  
✅ Simple YAML Syntax  
✅ Idempotent Operations  
✅ Easy to Learn  
✅ Powerful Automation  
✅ Scalable Infrastructure Management  

---

# ⚙️ How Ansible Works

Ansible works using:

- **Control Node** → The machine where Ansible is installed
- **Managed Nodes** → Target servers
- **Inventory File** → List of servers
- **Playbooks** → YAML files that define tasks

Flow:

1️⃣ Write Playbook  
2️⃣ Define Inventory  
3️⃣ Run Playbook  
4️⃣ Execute Tasks on Remote Machines  

---

# 📂 Project Structure

```
ansible-project/
│── inventory
│── playbook.yml
│── ansible.cfg
│── roles/
│── README.md
```

---

# 🛠️ Installation (Ubuntu/Linux)

```bash
# Update system
sudo apt update

# Install Ansible
sudo apt install ansible -y
```

---

# ✅ Verify Installation

```bash
ansible --version
```

Example Output:
```
ansible [core 2.x]
```

---

# 🧠 Core Ansible Concepts

## 1️⃣ Inventory

Defines target machines.

Example (`inventory` file):

```ini
[web]
192.168.1.10
192.168.1.11

[db]
192.168.1.20
```

---

## 2️⃣ Ad-Hoc Commands

Quick one-line automation commands.

```bash
ansible all -m ping
```

---

## 3️⃣ Playbook

Defines automation tasks in YAML format.

Example (`playbook.yml`):

```yaml
- name: Install Apache
  hosts: web
  become: yes

  tasks:
    - name: Install Apache package
      apt:
        name: apache2
        state: present
```

Run Playbook:

```bash
ansible-playbook -i inventory playbook.yml
```

---

## 4️⃣ Modules

Ansible uses modules to perform tasks.

Common modules:

- apt
- yum
- copy
- file
- service
- user
- git

Example:

```yaml
- name: Start Apache
  service:
    name: apache2
    state: started
```

---

## 5️⃣ Roles

Roles organize playbooks into reusable structures.

Example:

```
roles/
│── webserver/
│    │── tasks/
│    │── handlers/
│    │── templates/
│    │── vars/
```

---

# 🔁 Ansible Execution Flow

Ansible performs:

👉 Connect via SSH  
👉 Check current system state  
👉 Apply only necessary changes  

This ensures **Idempotency** (no duplicate changes).

---

# 🔒 Best Practices

✔️ Use SSH Key Authentication  
✔️ Organize using Roles  
✔️ Keep Secrets in Ansible Vault  
✔️ Use Separate Inventory for Dev/Prod  
✔️ Maintain Version Control (Git)  

---

# 🔐 Ansible Vault (For Secrets)

Encrypt sensitive data:

```bash
ansible-vault create secrets.yml
```

Edit encrypted file:

```bash
ansible-vault edit secrets.yml
```

Run with vault password:

```bash
ansible-playbook playbook.yml --ask-vault-pass
```

---

# 🌐 Where Ansible is Used

- Cloud Automation (AWS, Azure, GCP)
- CI/CD Pipelines
- Kubernetes Configuration
- DevOps Workflows
- Server Management
- Security Automation

---

# 🎯 Summary

Ansible is a powerful automation tool that simplifies configuration management and deployment.

It enables DevOps engineers to:

- Automate repetitive tasks
- Maintain consistent environments
- Reduce human errors
- Improve operational efficiency

---

