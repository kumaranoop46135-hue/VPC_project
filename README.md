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
- internet attached on public

## same proccess is nat gateway and connect private sub

<img width="755" height="470" alt="image" src="https://github.com/user-attachments/assets/647f840a-735e-455d-a7f8-6a7109d104ed" />

---

<img width="757" height="737" alt="image" src="https://github.com/user-attachments/assets/60c3e24c-e77a-4e96-92c3-6631ede65275" />

---

<img width="743" height="305" alt="image" src="https://github.com/user-attachments/assets/1164bb13-3868-4651-b7f9-93661a1014be" />

---

## 1.Associate Public Subnet with Public Route Table
- Select Public-route-Myvpc10
- Go to Subnet Associations
- Click Edit Subnet Associations
- Select Public-subnet
- Click Save
  ## 1.1>Associate public subnet with public Route Table ka Matlab hota
hai:
- Public Subnet Ko us Route Table se Connect (Attach) karna jisme Internet Gatway(IGW) Ka
RouteAdded ho.
- Simple language mein
- Jab tak ap Public subnet ko Public Route Table ke saath associate nahi karte tab tak;
- ➢ Subnet internet use nahi ker payega
- ➢ EC2 public subnet me hoke bhi internet nahi chalega 

# 2.Associate Private Subnet with Private Route Table
## ➢ After you create route table than create internet getway or
nat gatway
- Select Private-Route-Myvpc10
- Go to Subnet Associations
- Click Edit Subnet Associations
- Select Private-subnet
- Click Save
## 2.1>Associate private subnet with private Route Table ka Matlab Hota hai
Private Subnet ko us Route Table se connect (Attach) karna jisme nat gatways ka Route
Added ho.
# Launch EC2 in Public Subnet or private subnet
- Click on Ec2
- E nter name and tags
- Select any os like Amazon linux
- Enter key, key pair is same public or private ec2
- Click network Edit
- Select your Vpc Myvpc10
- Select your subnet agar aap public ec2 bana rahe hei tu public subnet select karo or
agar aap private ec2 bana rahe ho to private subnet select karo
- Public (Auto-assign)(Enable karna hei)
- Private (Auto-assign)(Disable karna hei)
- Security group rule SSh,HTTP,(source 0.0.0.0/0)(Source Type ANYWHERE)
- Select configure Storage (20GiB)
- Click on Launch Instance

---
## this way to login or ssh your ec2 to powershell 

<img width="1806" height="862" alt="image" src="https://github.com/user-attachments/assets/4a0c8b6b-6b0a-4b18-bda9-203e1467d477" />

---

## step by step all command and build httpd server 1 $ server 2
- ssh -i "ppp.pem" ec2-user@10.0.1.219 (this is main command to connect private ec2 to public and after taht you are login private ec2)
- vim ppp.pem (this is a key command go to download folder and copy key and past)
- sudo yum install httpd
- sudo systemctl start httpd
- sudo systemctl enable httpd
-  cd /var/www/html
-  sudo nano index.html

---

 # NEXT STEP TO CREAT A TARGET GROUP 

 <img width="1919" height="1078" alt="image" src="https://github.com/user-attachments/assets/aebfffee-0c6f-4107-ac1c-3be9abced045" />
 ALL target is healthy that all fine 

---

 # next step to creat a load blancer 

 <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/602195a3-a4e7-4925-8d26-c4a3667cca17" />

 ---

 ## NEXT STEP AND FINAL STEP 
 - COPY DNS AND PAST CHROME
 - AND CLICK ON THE REFRESH BUTTON 

---

# thats good your are creat your vpc project successfuly creat with load blancer 

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5c89897b-9338-4475-bbb5-c13fbdd0042e" />

---

<img width="1917" height="1079" alt="image" src="https://github.com/user-attachments/assets/0ab284c5-679a-4479-a183-6eb015cf0d23" />

---

## Author 
# Anoop kumar
