# Amazon Aurora Database with EC2

This project shows how to create an **Amazon Aurora MySQL Database** and connect it with an **Amazon EC2 instance**.

It is a beginner-friendly AWS project that helps you understand how databases work with web servers.

---

## 📖 Project Overview

In this project, I learned how to:

- Create an Amazon Aurora MySQL database
- Launch an Amazon EC2 instance
- Connect the Aurora database to the EC2 instance
- Prepare the infrastructure for hosting a web application

---

## 🛠 AWS Services Used

- Amazon Aurora (MySQL)
- Amazon RDS
- Amazon EC2
- IAM
- VPC
- Security Groups

---

## 📐 Architecture

```
        +-------------------+
        |   Amazon EC2      |
        |  (Web Server)     |
        +---------+---------+
                  |
                  |
                  |
        +---------v---------+
        | Amazon Aurora     |
        | MySQL Database    |
        +-------------------+
```

---

## 🚀 Steps Performed

### Step 1: Login

- Logged into AWS using an IAM user.

---

### Step 2: Create Aurora Database

- Opened Amazon RDS Console.
- Selected **Aurora MySQL**.
- Used the **Dev/Test** template.
- Created a database cluster.
- Set the database username and password.

---

### Step 3: Launch EC2 Instance

Created an EC2 instance with:

- Amazon Linux 2023
- t2.micro instance
- New Key Pair
- Enabled SSH
- Enabled HTTP traffic

---

### Step 4: Connect EC2 to Aurora

- Connected the Aurora database with the EC2 instance.
- Created the database successfully.
- Waited until the database status became **Available**.

---

## 🎯 What I Learned

- What Amazon Aurora is
- Difference between Aurora and traditional databases
- How EC2 acts as a web server
- How to connect AWS services together
- Basic AWS networking concepts

---

## 💡 Key Concepts

### Amazon Aurora

Amazon Aurora is a managed relational database service provided by AWS. It is compatible with MySQL and PostgreSQL and offers high performance and high availability.

### Amazon EC2

Amazon EC2 is a virtual server in the cloud used to run applications.

### Relational Database

A relational database stores data in tables made up of rows and columns.

---

## 📷 Screenshots

Add your screenshots here.

Example:

- Aurora Database Configuration
- EC2 Instance
- Database Connected to EC2
- Aurora Cluster
- AWS Console

---

## 🧹 Clean Up

To avoid AWS charges, delete:

- Aurora Database Cluster
- EC2 Instance
- Key Pair
- Any unused Security Groups

---


## 📚 Skills Gained

- AWS Aurora
- Amazon EC2
- Amazon RDS
- IAM
- Database Management
- Cloud Networking
- AWS Basics

---

## 👨‍💻 Author

**Mudasir Ahmad**
