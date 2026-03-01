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

---
<img width="833" height="512" alt="image" src="https://github.com/user-attachments/assets/866ae458-458d-4af6-8873-9c28770a5365" />

---
<img width="830" height="654" alt="image" src="https://github.com/user-attachments/assets/49c8ceec-a764-404f-bab1-099aeae2de1a" />

---
## Create Public Subnet
- Go to Subnets
- Click Create Subnet
- Select VPC:myvpc10
- Enter : Subnet name: public-subnet
- Select any region example
- CIDR:10.0.1.0/24
  
## Create private subnet
- Go to Subnets
- Click Create Subnet
- Select VPC:Myvpc10
- Enter: subnet name : Private-subnet
- Select any region example
- CIDR: 10.0.2.0/24
---
  # Minimum public subnet is (1) & Minimum private Subnet is (2)
  <img width="827" height="724" alt="image" src="https://github.com/user-attachments/assets/8e561186-65b5-4a8d-9ea0-5a85c8e65701" />

---
# Create Route Table for Public Subnet or private subnet
- Go to Route Tables
- Click Create Route Table
- Name: Public-route-Myvpc10
- Select VPC: Myvpc
- Click Create

  ---
## Now add route
- Select public-route-Myvpc-10
- Go to Routes tab
- Click Edit routes
- Add route; Destination 0.0.0.0/0
- Target: Internet gateway
- Click Save 
## SAME PROCESS IS PRIVATE ROUTE TABLE
---

## Create Internet Gateways
- Click internet gateways
- Name: internet-MyVpc10
- Click create
- Now to Attached on MYvpc
