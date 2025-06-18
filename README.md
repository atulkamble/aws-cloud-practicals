## 📓 AWS Practical Task List (with categories)

### 📁 **01-EC2**

* **Task 1**: Launch an EC2 Instance using Console & CLI
* **Task 2**: Install a web server (Apache/NGINX) on EC2
* **Task 3**: Attach & mount EBS volume to EC2 instance
* **Task 4**: Create an AMI from an EC2 instance

---

### 📁 **02-S3**

* **Task 5**: Create a versioned S3 bucket and upload files
* **Task 6**: Enable static website hosting on S3
* **Task 7**: Configure S3 bucket policy to make it public/private

---

### 📁 **03-VPC**

* **Task 8**: Create a custom VPC with public and private subnets
* **Task 9**: Configure internet gateway and NAT gateway
* **Task 10**: Launch an EC2 in a private subnet via Bastion Host

---

### 📁 **04-IAM**

* **Task 11**: Create an IAM user, group, and attach policies
* **Task 12**: Generate access keys and configure AWS CLI

---

### 📁 **05-Lambda**

* **Task 13**: Create a Lambda function triggered by S3 file upload
* **Task 14**: Create an API Gateway endpoint to invoke a Lambda function

---

### 📁 **06-CloudFormation**

* **Task 15**: Write a CloudFormation template to deploy a VPC + EC2 + Security Group
* **Task 16**: Use nested stacks to deploy a multi-tier app infrastructure

---

### 📁 **07-Terraform (Bonus DevOps Tasks)**

* **Task 17**: Write Terraform code to provision EC2 + Security Group
* **Task 18**: Terraform code for S3 + CloudFront for static website

---

### 📁 **08-ECS/EKS (Optional Advanced)**

* **Task 19**: Deploy a Dockerized app to ECS
* **Task 20**: Provision an EKS cluster and deploy a Kubernetes app

---

## 📌 Suggested Repo Structure:

```
aws-cloud-practicals/
├── README.md
├── EC2/
│   └── launch-ec2-cli.md
├── S3/
│   └── static-website-hosting.md
├── VPC/
│   └── custom-vpc-setup.md
├── IAM/
│   └── iam-user-policy.md
├── Lambda/
│   └── lambda-s3-trigger.md
├── CloudFormation/
│   └── vpc-ec2-template.yaml
├── Terraform/
│   └── ec2-instance.tf
└── ECS/
    └── dockerized-app-ecs.md
```

---

## 📑 Bonus: Add a `README.md` like

```markdown
# AWS Cloud Practicals 🚀

This repository contains hands-on practical AWS tasks for learning and portfolio building. Suitable for Cloud Architects, DevOps Engineers, and AWS enthusiasts.

## 📚 Topics Covered:
- EC2
- S3
- VPC
- IAM
- Lambda
- CloudFormation
- Terraform
- ECS/EKS

## 🔗 Getting Started
Clone the repository and follow each lab task in the respective folders.

```
