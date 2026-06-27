# AWS RDS Practical Guide | Relational Database in the Cloud

A hands-on guide to **Amazon Relational Database Service (RDS)** that demonstrates how to deploy, configure, and manage a relational database in the AWS Cloud.

## 📖 Overview

This project introduces the core features of Amazon RDS, including database creation, connectivity, security, monitoring, and backups. It is designed for beginners who want practical experience with AWS-managed databases.

## 🚀 What You'll Learn

* Create an Amazon RDS instance
* Configure networking and security groups
* Connect to the database using MySQL Workbench or pgAdmin
* Execute basic SQL operations
* Monitor database performance with CloudWatch
* Create backups and restore from snapshots
* Understand Multi-AZ deployments and Read Replicas

## 🛠 Technologies Used

* Amazon Web Services (AWS)
* Amazon RDS
* MySQL / PostgreSQL
* AWS CloudWatch
* Docker
* MySQL Workbench / pgAdmin

## 📂 Project Structure

```text
AWS-RDS-Practical-Guide/
├── README.md
├── screenshots/
├── sql/
└── notes/
```

## ▶️ Getting Started

1. Launch an EC2 instance.
2. Create an Amazon RDS database.
3. Configure Security Groups and networking.
4. Connect the application to the RDS database.
5. Run the Docker container.

### Docker Setup on Amazon Linux

```bash
sudo yum install docker -y

sudo service docker start

sudo usermod -aG docker ec2-user

sudo docker pull philippaul/node-mysql-app:02
```

## 🔒 Best Practices

* Restrict database access using Security Groups.
* Enable automated backups.
* Use strong credentials and encryption.
* Monitor database performance regularly.

## 👨‍💻 Author

**Mudasir Ahmad**
GitHub: **@anberlin**

## 📜 License

This project is licensed under the MIT License.
