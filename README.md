# ☁️ AWS VPC Complete Setup with Public & Private Subnet

## 📖 Introduction
In this project, I explain how to create a **Virtual Private Cloud (VPC)** in AWS step by step.  
VPC helps us create a secure private network in the cloud where we can launch EC2 instances, create subnets, configure internet gateways, route tables, and more.

This project demonstrates basic cloud networking concepts used in real-world DevOps environments.

---

## 🌐 What is VPC?

A **Virtual Private Cloud (VPC)** is a private network inside AWS.  
It is like our own personal network where we can securely deploy cloud resources.

Inside a VPC we can create:

- Public Subnet  
- Private Subnet  
- Route Tables  
- Internet Gateway  
- Security Groups  
- Load Balancer  

---
## ❓ Why We Use VPC?

We use VPC because:

- It provides strong network security  
- We can control IP address ranges using CIDR blocks  
- We can separate resources into public and private networks  
- It helps to build secure real-world cloud architectures  

---
##  VPC Architecture  
<img width="692" height="370" alt="image" src="https://github.com/user-attachments/assets/a9344ef8-a724-4826-aac2-da016a185011" />

-----

## Step to login AWS console 
- Go to AWS console
- Search VPC
- Open VPC Dashboard

## Step to Create VPC
- Click create VPC
- Select VPC only
- Enter Name :Myvpc10
- IPv4 CIDR:10.0.0.0/16
- Click create VPC

  ---

<img width="839" height="831" alt="image" src="https://github.com/user-attachments/assets/f68c5aa2-0896-410f-8c33-95370aa4e4ea" />

