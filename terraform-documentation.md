# 🌍 🚀 Terraform Infrastructure as Code (IaC) Project

![Terraform](https://img.shields.io/badge/Terraform-v1.14.5-7B42BC?style=for-the-badge&logo=terraform)
![Platform](https://img.shields.io/badge/Platform-Linux-2CA5E0?style=for-the-badge&logo=linux)
![IaC](https://img.shields.io/badge/Infrastructure-as%20Code-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

---

# 📌 What is Terraform?

Terraform is an open-source **Infrastructure as Code (IaC)** tool developed by HashiCorp.  
It allows you to define, provision, and manage infrastructure using configuration files instead of manually creating resources.

With Terraform, you can manage:

- 🖥️ Virtual Machines (EC2, Azure VM, GCP Compute)
- 🌐 Networking (VPC, Subnets, Security Groups)
- 🗄️ Storage (S3, Blob Storage)
- 🐳 Containers (Kubernetes, Docker)
- ☁️ Multi-Cloud Infrastructure

Terraform uses **declarative language (HCL - HashiCorp Configuration Language)**.

---

# 🏗️ Why Use Terraform?

✅ Infrastructure as Code  
✅ Automation & Repeatability  
✅ Version Control Friendly  
✅ Multi-Cloud Support  
✅ Easy Rollback & Change Tracking  
✅ Consistent Environment Setup  

---

# ⚙️ Terraform Architecture

Terraform works in the following stages:

1️⃣ **Write** – Define infrastructure in `.tf` files  
2️⃣ **Plan** – Preview changes before applying  
3️⃣ **Apply** – Provision infrastructure  
4️⃣ **Destroy** – Remove infrastructure safely  

Terraform interacts with cloud providers using **Providers** (AWS, Azure, GCP, etc.).

---

# 📂 Project Structure

```
terraform-project/
│── main.tf        # Main infrastructure configuration
│── variables.tf   # Input variables
│── outputs.tf     # Output values
│── terraform.tfvars  # Variable values
│── README.md
```

---

# 🛠️ Installation (Ubuntu/Linux)

```bash
# Update system
sudo apt update

# Add HashiCorp GPG key
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add repository
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

# Install Terraform
sudo apt update && sudo apt install terraform -y
```

---

# ✅ Verify Installation

```bash
terraform --version
```

Example Output:
```
Terraform v1.14.5
on linux_amd64
```

---

# 🧠 Core Terraform Concepts

## 1️⃣ Provider

A provider is responsible for understanding API interactions and exposing resources.

Example:
```hcl
provider "aws" {
  region = "us-east-1"
}
```

---

## 2️⃣ Resource

Resources define infrastructure components.

Example:
```hcl
resource "aws_instance" "my_server" {
  ami           = "ami-123456"
  instance_type = "t2.micro"
}
```

---

## 3️⃣ Variables

Used to make configuration reusable and dynamic.

```hcl
variable "instance_type" {
  default = "t2.micro"
}
```

---

## 4️⃣ Output Values

Displays important information after deployment.

```hcl
output "instance_ip" {
  value = aws_instance.my_server.public_ip
}
```

---

## 5️⃣ State File

Terraform maintains a `terraform.tfstate` file.

- Tracks infrastructure changes
- Maps real resources to configuration
- Should be stored securely
- Can be stored remotely (S3 backend)

---

# 🚀 Terraform Workflow Commands

```bash
terraform init      # Initialize project & download providers
terraform validate  # Validate configuration syntax
terraform plan      # Show execution plan
terraform apply     # Apply changes
terraform show      # Show current state
terraform destroy   # Destroy infrastructure
```

---

# 🔁 Terraform Lifecycle

Terraform compares:

👉 Current State  
👉 Desired Configuration  

Then it performs only the necessary changes.

This ensures:

- Minimal downtime
- Safe updates
- Predictable infrastructure management

---

# 🌐 Supported Cloud Providers

- AWS
- Microsoft Azure
- Google Cloud Platform
- Oracle Cloud
- DigitalOcean
- Kubernetes
- Many more...

---

# 🔒 Best Practices

✔️ Use Remote Backend (S3 + DynamoDB)  
✔️ Use Modules for Reusability  
✔️ Keep Secrets in Environment Variables  
✔️ Use Version Control (Git)  
✔️ Separate Dev / Staging / Production  

---

# 🎯 Summary

Terraform enables DevOps engineers to automate infrastructure provisioning efficiently and consistently.

It reduces manual work, improves reliability, and ensures infrastructure can be recreated anytime using code.

---

