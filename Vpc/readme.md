# AWS VPC Setup

This project demonstrates how to create and configure a basic **Amazon Virtual Private Cloud (VPC)** with public and private subnets. It provides a secure and scalable networking foundation for deploying cloud resources.

---

## 📖 Overview

A **Virtual Private Cloud (VPC)** is a logically isolated network within AWS where you can securely launch AWS resources. It allows you to define your own networking environment, including IP address ranges, subnets, routing, and internet connectivity.

This guide walks through creating:

- A custom VPC
- Public and private subnets
- Route tables
- Internet Gateway
- Internet connectivity for public resources
- A secure network layout for deploying applications

---

## 🚀 Features

- Create a dedicated VPC
- Public and private subnet architecture
- Internet Gateway configuration
- Custom Route Table
- Internet access for public subnet
- Secure private subnet for backend resources
- Multi-AZ ready design
- AWS best practices

---

## 🏗️ Architecture

```text
                          Internet
                              │
                      Internet Gateway
                              │
                      Public Route Table
                              │
                 ┌────────────────────┐
                 │        VPC         │
                 │    10.0.0.0/16     │
                 └────────────────────┘
                     │             │
                     │             │
           Public Subnet      Private Subnet
            10.0.1.0/24         10.0.2.0/24
                  │                  │
          Internet-facing      Internal Resources
             Resources         (App, DB, API)
```

---

## 📦 Components

| Component | Description |
|-----------|-------------|
| **VPC** | Isolated virtual network |
| **Public Subnet** | Hosts internet-facing resources |
| **Private Subnet** | Hosts backend services and databases |
| **Internet Gateway** | Enables internet connectivity |
| **Route Table** | Controls network routing |
| **Security Groups** | Instance-level firewall |
| **Network ACLs** | Subnet-level firewall |

---

## 📁 Network Layout

| Resource | CIDR |
|----------|------|
| VPC | `10.0.0.0/16` |
| Public Subnet | `10.0.1.0/24` |
| Private Subnet | `10.0.2.0/24` |

---

## ⚙️ Prerequisites

- AWS Account
- IAM User with VPC permissions
- AWS Management Console access

---

# Step 1 — Create a VPC

Navigate to:

```
AWS Console → VPC → Create VPC
```

Configuration:

| Setting | Value |
|---------|-------|
| Resources to create | VPC only |
| Name | my-vpc |
| IPv4 CIDR | 10.0.0.0/16 |

Click **Create VPC**.

---

# Step 2 — Create Public & Private Subnets

Navigate to:

```
VPC → Subnets → Create Subnet
```

### Public Subnet

| Setting | Value |
|---------|-------|
| Name | public-subnet |
| Availability Zone | Your preferred AZ |
| CIDR | 10.0.1.0/24 |

### Private Subnet

| Setting | Value |
|---------|-------|
| Name | private-subnet |
| Availability Zone | Your preferred AZ |
| CIDR | 10.0.2.0/24 |

Click **Create Subnet**.

---

# Step 3 — Create a Route Table

Navigate to:

```
VPC → Route Tables → Create Route Table
```

Configuration:

| Setting | Value |
|---------|-------|
| Name | my-route-table |
| VPC | my-vpc |

---

# Step 4 — Create an Internet Gateway

Navigate to:

```
VPC → Internet Gateways
```

Click **Create Internet Gateway**.

Configuration:

| Setting | Value |
|---------|-------|
| Name | my-internet-gateway |

---

# Step 5 — Attach the Internet Gateway

Select the Internet Gateway.

Choose:

```
Actions
    ↓
Attach to VPC
```

Select your VPC and click **Attach**.

---

# Step 6 — Associate Public Subnet

Open your Route Table.

Select:

```
Subnet Associations
```

Click **Edit**.

Select:

```
public-subnet
```

Save the changes.

---

# Step 7 — Add Internet Route

Open:

```
Route Table
```

Go to:

```
Routes
```

Click:

```
Edit Routes
```

Add:

| Destination | Target |
|-------------|--------|
| 0.0.0.0/0 | Internet Gateway |

Save changes.

---

# Step 8 — Verify

Open:

```
VPC → Resource Map
```

You should see:

- ✅ VPC
- ✅ Public Subnet
- ✅ Private Subnet
- ✅ Route Table
- ✅ Internet Gateway
- ✅ Public subnet connected to the Internet

---

# Deploy Resources

### Public Subnet

Deploy resources such as:

- Web Server
- Bastion Host
- Load Balancer

These resources are accessible from the internet.

---

### Private Subnet

Deploy internal resources such as:

- Application Server
- Database
- Cache Server
- Internal APIs

These resources are not directly accessible from the internet.

---

## 🌐 CIDR Reference

Need help understanding CIDR notation?

Visit:

https://cidr.xyz/

---

## 📌 Best Practices

- Keep databases in private subnets.
- Use Security Groups with least-privilege access.
- Use meaningful names and tags.
- Avoid overlapping CIDR blocks.
- Deploy resources across multiple Availability Zones.
- Use a NAT Gateway if private resources require outbound internet access.

---

## 📚 References

- AWS VPC Documentation
- AWS Networking Best Practices
- https://docs.aws.amazon.com/vpc/
- You can see the screenshots as well for reference.

---

## 📄 License

This project is intended for learning and demonstration purposes.
Mudasir Ahmad // @anberlin

# Steps: 
GO to the vpc 
# click on create new vpc 
VPC settings = vpc only 
Name tag - my-vpc (you can give your name )
IPv4 CIDR   -- 10.0.0.0/16 (you can choose your requirmnet )
click on create vpc 
check the resouce map nothing is connected 
# Now lets create subnets 
select your VPC i will select mine
Subnet 1 of 1 
Subnet name Public-subnet  (you can give your name )
Availability Zone = asia pasfic sydney  (you can give your )
IPv4 subnet CIDR block = 10.0.1.0/24   (you can choose your requirmnet )

CLick on add new subnet
Subnet 2 of 2 = 
Subnet name private-subnet  (you can give your name )
Availability Zone = asia pasfic sydney  (you can give your )
IPv4 subnet CIDR block = 10.0.2.0/24   (you can choose your requirmnet )

click on create subnet
by default it will assign route table

# Now lets create route table
click on router then create routue table
Create route table: Name - my-route-table
select your : VPC


now After that create internet gateway
go internet gateway click 
Create internet gateway
Internet gateway settings
Name :my-internet-gateway
click and create internet gateway

# Now after that go to internet gateway click on attach internet gateway or click action to attach 
select your Available VPCs =name of your vpc
click attach

now go to route table and click on the my-route-table and get deatils 
and select subnet association 
Edit subnet associations
Change which subnets are associated with this route table.
select public-subnet (i want to connect to network)
click save 

# Now go to route table then routes 
then click on edit route 
Add Route2 Destination  0.0.0.0/0  and  select tasrget internet gateway
save changes 
Now go to vpc and then id and check Resouce map 
now u will see routable connect of public internet gateway 

# Now we will create the subnet in private subnet 
name server and then go to network setting and select your private subnet for your data 



