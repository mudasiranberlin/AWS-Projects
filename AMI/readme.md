# Amazon Machine Image (AMI) Overview

## What is an AMI?

An **Amazon Machine Image (AMI)** is a pre-configured template used to launch virtual servers (EC2 instances) in Amazon Web Services (AWS). It includes the operating system, software packages, configuration settings, and permissions required to run an instance.

Using an AMI allows you to quickly deploy consistent and repeatable environments in the cloud.

---

## Key Features

- Pre-installed operating system (Linux, Windows, etc.)
- Pre-configured software and dependencies
- Customizable for specific applications
- Fast and scalable instance deployment
- Reusable templates for multiple environments

---

## Components of an AMI

An AMI consists of three main parts:

1. **Root Volume Template**  
   Contains the operating system and installed software.

2. **Launch Permissions**  
   Defines which AWS accounts can use the AMI.

3. **Block Device Mapping**  
   Specifies storage volumes attached to the instance.

---

## How to Use an AMI

### 1. Launch an EC2 Instance
- Go to the AWS Management Console
- Navigate to **EC2 Dashboard**
- Click **Launch Instance**
- Select an AMI

### 2. Configure Instance
- Choose instance type
- Configure network and storage settings
- Add security groups

### 3. Connect to Instance
- Use SSH (Linux) or RDP (Windows)
- Verify application and environment setup

---

## Creating a Custom AMI

1. Launch and configure an EC2 instance
2. Install required software and dependencies
3. Stop the instance (optional but recommended)
4. Select **Create Image** from the EC2 console
5. Use the new AMI to launch identical instances

---

## Use Cases

- Deploying web applications
- Setting up development or testing environments
- Scaling production systems
- Backup and recovery of server configurations

---

## Advantages

- Saves setup time
- Ensures consistent environments
- Simplifies scaling
- Reduces configuration errors

---

## Notes

- AMIs are region-specific in AWS
- Custom AMIs may incur storage costs (EBS snapshots)
- Always manage permissions carefully for shared AMIs

---

## Author 

Mudasir Ahmad /@Anberlin
