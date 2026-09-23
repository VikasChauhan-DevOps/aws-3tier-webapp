# 🚀 Highly Available 3-Tier Web Application on AWS

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws&logoColor=white)
![CloudFormation](https://img.shields.io/badge/AWS-CloudFormation-orange?logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/Amazon-EC2-orange?logo=amazonaws&logoColor=white)
![RDS](https://img.shields.io/badge/Amazon-RDS-orange?logo=amazonaws&logoColor=white)
![VPC](https://img.shields.io/badge/Amazon-VPC-orange?logo=amazonaws&logoColor=white)
![IaC](https://img.shields.io/badge/Infrastructure-as--Code-blue)

## 📌 Project Status

**Architecture Design & Infrastructure Showcase**

This project demonstrates the design of a Highly Available 3-Tier Web Application architecture on AWS using Infrastructure as Code concepts and AWS CloudFormation.

> **Note:** The AWS infrastructure in this repository is presented as an architecture and reference implementation showcase. It has not been deployed or validated in the user's AWS account.

---

## ☁️ Project Overview

This project showcases how a scalable and highly available web application can be designed on AWS using a secure 3-tier architecture across multiple Availability Zones.

### Architecture Layers

- 🌐 **Presentation Layer** — Application Load Balancer (ALB)
- 💻 **Application Layer** — EC2 + Auto Scaling Group
- 🗄️ **Database Layer** — Amazon RDS (MySQL)
- 📦 **Storage Layer** — Amazon S3
- 📊 **Monitoring** — Amazon CloudWatch
- 🛠️ **Infrastructure as Code** — AWS CloudFormation

---

## 🛠️ AWS Services Used

| Service | Purpose |
|---------|---------|
| Amazon VPC | Networking |
| Public & Private Subnets | Network segmentation |
| Internet Gateway | Public internet access |
| NAT Gateway | Outbound internet access for private subnets |
| Application Load Balancer | Traffic distribution |
| Amazon EC2 | Application servers |
| Auto Scaling Group | Application scalability and high availability |
| Amazon RDS | MySQL database |
| Amazon S3 | Static assets and storage |
| IAM | Access management |
| Amazon CloudWatch | Monitoring and observability |
| AWS CloudFormation | Infrastructure as Code |

---

## 🏗️ Architecture Diagram

![AWS Architecture](diagrams/architecture.png)

> **Architecture:** Highly Available 3-Tier Web Application on AWS

---

## 🔄 Architecture Flow

```text
                    🌐 User
                       │
                       ▼
            ┌──────────────────────┐
            │ Application Load     │
            │ Balancer (ALB)       │
            └──────────┬───────────┘
                       │
              ┌────────┴────────┐
              ▼                 ▼
       ┌─────────────┐   ┌─────────────┐
       │ EC2 / ASG   │   │ EC2 / ASG   │
       │    AZ-A     │   │    AZ-B     │
       └──────┬──────┘   └──────┬──────┘
              │                 │
              └────────┬────────┘
                       ▼
              ┌─────────────────┐
              │   Amazon RDS    │
              │   Private DB    │
              └─────────────────┘
```

### Request Flow

1. A user request is received by the Application Load Balancer.
2. The ALB distributes traffic across application servers in multiple Availability Zones.
3. EC2 application servers process the request.
4. The application layer communicates with the private RDS database when database access is required.
5. Amazon S3 can be used for application assets and storage.
6. Amazon CloudWatch is used for monitoring and observability.

---

## ☁️ Infrastructure as Code

The repository includes a CloudFormation reference template covering the main components of the 3-tier architecture.

**CloudFormation Template:**

[View CloudFormation Template](cloudformation/3-tier-architecture-showcase.yaml)

### Template Scope

- VPC and subnet design
- Internet Gateway
- NAT Gateways
- Route tables
- Security groups
- IAM role and instance profile
- Application Load Balancer
- Target group and listener
- EC2 Launch Template
- Auto Scaling Group
- Amazon RDS
- Amazon S3

> The template is included as a reference/showcase artifact and should be reviewed and validated before any real AWS deployment.

---

## 📂 Project Structure

```text
aws-3tier-webapp/
│
├── cloudformation/
│   └── 3-tier-architecture-showcase.yaml
│
├── diagrams/
│   └── architecture.png
│
├── README.md
└── LICENSE
```

### 📁 Directory Overview

| Directory / File | Purpose |
|------------------|---------|
| `cloudformation/` | AWS CloudFormation infrastructure template |
| `diagrams/` | AWS architecture diagrams |
| `README.md` | Project documentation |
| `LICENSE` | Repository license |

---

## 🎯 Key Design Goals

- Multi-AZ architecture
- Separation of public, application, and database layers
- Controlled network access using security groups
- Scalable application tier using Auto Scaling
- Load-balanced application traffic
- Private database layer
- Infrastructure automation using CloudFormation

---

## 🧠 What I Learned

Through this project, I practiced:

- Designing a 3-tier AWS architecture
- Planning VPC and subnet layouts
- Understanding public and private networking
- Designing multi-AZ application infrastructure
- Understanding ALB and Auto Scaling architecture
- Planning a private RDS database layer
- Organizing infrastructure as code with CloudFormation
- Documenting cloud architecture in GitHub

---

## 🚀 Planned Implementation Flow

```text
Architecture Design
        ↓
VPC & Networking
        ↓
Security Groups & IAM
        ↓
ALB & Target Group
        ↓
EC2 & Auto Scaling
        ↓
RDS Database
        ↓
S3 Storage
        ↓
CloudWatch Monitoring
        ↓
CloudFormation Automation
```

---

## 📌 Portfolio Note

This repository is maintained as a **DevOps / AWS architecture showcase**. The current version focuses on architecture design, infrastructure organization, and CloudFormation reference implementation.

---

## 👨‍💻 Author

**Vikas Chauhan**

DevOps Engineer

GitHub: [VikasChauhan-DevOps](https://github.com/VikasChauhan-DevOps)

LinkedIn: [Vikas Chauhan - DevOps](https://www.linkedin.com/in/vikaschauhan-devops)
