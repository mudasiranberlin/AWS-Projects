# VPC

## Overview

The VPC (Virtual Private Cloud) provides an isolated network environment for deploying cloud resources securely. It serves as the foundation for the infrastructure by defining the network, subnets, routing, and internet connectivity.

## Features

- Creates a dedicated Virtual Private Cloud (VPC)
- Supports public and private subnets
- Internet connectivity through an Internet Gateway
- Private subnet internet access via NAT Gateway (optional)
- Route tables for public and private traffic
- DNS resolution and hostname support
- Resource tagging for organization and management
- Designed for high availability across multiple Availability Zones

## Architecture

```text
                    Internet
                        │
                Internet Gateway
                        │
                  ┌────────────┐
                  │    VPC     │
                  └────────────┘
                  /            \
         Public Subnets     Private Subnets
              │                    │
      Internet-facing        Internal Resources
         Resources
```

## Components

- **VPC** – Isolated virtual network.
- **Public Subnets** – Used for resources that require internet access.
- **Private Subnets** – Used for internal services and databases.
- **Internet Gateway** – Enables internet connectivity for public resources.
- **NAT Gateway (Optional)** – Allows outbound internet access for private resources.
- **Route Tables** – Control network traffic between subnets and external networks.
- **Security Groups and Network ACLs** – Provide network-level security.

## Network Flow

- Public resources communicate with the internet through the Internet Gateway.
- Private resources access the internet through the NAT Gateway (if enabled).
- Communication between resources within the VPC remains private.

## Best Practices

- Separate public and private workloads.
- Use private subnets for databases and internal services.
- Enable DNS support for service discovery.
- Apply least-privilege security group rules.
- Use consistent resource naming and tagging.
- Deploy across multiple Availability Zones for improved availability.


## Notes

- Ensure that subnet CIDR ranges do not overlap.
- Use appropriate routing and security rules based on application requirements.
- Review networking configurations before deployment to ensure they align with your architecture.

## Get more information on CIDR 
- Vist the website
- https://cidr.xyz/

