# <span style="color:#2E86C1;">Day 5 - AWS EC2 Instance Creation, Configuration and SSH Access</span>

---

## <span style="color:#28B463;">📘 Introduction</span>

On Day 5 of my DevOps learning journey, I worked with <span style="color:#F39C12;"><b>Amazon EC2 (Elastic Compute Cloud)</b></span>.  
I launched a cloud-based virtual server, configured networking and security settings, verified instance health status, and connected to it securely using SSH.

---

## <span style="color:#8E44AD;">☁ What is Amazon EC2?</span>

Amazon EC2 is a web service that provides resizable compute capacity in the cloud.  
It allows users to launch virtual machines (instances) that act as servers for hosting applications and services.

---

## <span style="color:#16A085;">🖥 AWS Environment Details</span>

- <b>Service Used:</b> Amazon EC2  
- <b>Region:</b> US East (N. Virginia)  
- <b>Instance Name:</b> sanjay  
- <b>Instance ID:</b> i-0885f260d9ab1ca94  
- <b>Instance Type:</b> t3.micro  
- <b>Availability Zone:</b> us-east-1c  
- <b>Public IPv4:</b> <span style="color:#C0392B;">54.172.217.113</span>  
- <b>Private IPv4:</b> 172.31.27.242  
- <b>Public DNS:</b> ec2-54-172-217-113.compute-1.amazonaws.com  
- <b>VPC ID:</b> vpc-0b3b1f0708ec23fa1  
- <b>Subnet ID:</b> subnet-00d00e83ea0e630e6  

---

## <span style="color:#D35400;">🚀 Step-by-Step Implementation</span>

### <span style="color:#1F618D;">Step 1: Login to AWS Console</span>

- Logged into AWS Management Console  
- Selected region: US East (N. Virginia)  
- Navigated to EC2 Dashboard  

---

### <span style="color:#1F618D;">Step 2: Launch EC2 Instance</span>

- Selected Ubuntu AMI  
- Chose instance type: t3.micro  
- Created/Selected Key Pair: <b>my_key.pem</b>  
- Configured Security Group:
  - Allowed SSH (Port 22)  
- Launched the instance  

Instance state changed from <span style="color:#E67E22;">Pending</span> to <span style="color:#27AE60;"><b>Running</b></span>.

---

### <span style="color:#1F618D;">Step 3: Instance Health Check</span>

- <span style="color:#27AE60;"><b>Instance State:</b> Running</span>  
- <span style="color:#27AE60;"><b>Status Checks:</b> 3/3 checks passed</span>  

This confirms the server is healthy.

---

## <span style="color:#9B59B6;">🔐 Connecting to EC2 via SSH</span>

### <span style="color:#34495E;">Set Permission for Key File</span>

```bash
chmod 400 my_key.pem
```

---

### <span style="color:#34495E;">SSH Connection Command</span>

```bash
ssh -i "my_key.pem" ubuntu@ec2-54-172-217-113.compute-1.amazonaws.com
```

Connection established successfully to the Linux server.

---

## <span style="color:#E74C3C;">🌐 Networking Concepts Understood</span>

- <b>Public IP:</b> Used to access instance from internet  
- <b>Private IP:</b> Used for internal AWS communication  
- <b>VPC:</b> Virtual network inside AWS  
- <b>Subnet:</b> Division inside VPC  
- <b>Security Group:</b> Virtual firewall controlling traffic  

---

## <span style="color:#2ECC71;">📚 Knowledge Gained</span>

- Launching and managing EC2 instances  
- Understanding cloud networking  
- Securing server access using key pairs  
- Configuring security groups  
- Using SSH to access Linux servers  
- Foundation for cloud deployment  

---

## <span style="color:#F1C40F;">🎯 Outcome</span>

Successfully launched and accessed an EC2 instance in AWS.  
This forms the <span style="color:#2E86C1;"><b>foundation for deploying applications on cloud infrastructure</b></span>.

---

## <span style="color:#AF7AC5;">🏁 Conclusion</span>

Day 5 focused on practical cloud infrastructure setup.  
This step prepares me for installing Docker, Jenkins, Nginx, and deploying real-time applications on AWS.

