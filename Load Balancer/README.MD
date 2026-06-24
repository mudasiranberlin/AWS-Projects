# AWS Load Balancing

## Overview

AWS Load Balancing distributes incoming application traffic across multiple targets such as Amazon EC2 instances, containers, IP addresses, and Lambda functions. It improves application availability, fault tolerance, scalability, and performance by ensuring that no single resource becomes overwhelmed.

AWS provides load balancing through **Elastic Load Balancing (ELB)**, a managed service that automatically distributes traffic and scales based on demand.

---

## Benefits

- High Availability
- Automatic Scaling
- Fault Tolerance
- Improved Application Performance
- SSL/TLS Termination
- Health Monitoring
- Reduced Single Points of Failure

---

## Types of AWS Load Balancers

### 1. Application Load Balancer (ALB)

Application Load Balancer operates at Layer 7 (HTTP/HTTPS) of the OSI model.

#### Features

- Content-based routing
- Host-based routing
- Path-based routing
- WebSocket support
- SSL/TLS termination
- Integration with containers and microservices

#### Use Cases

- Web applications
- REST APIs
- Microservices architectures
- Containerized applications

---

### 2. Network Load Balancer (NLB)

Network Load Balancer operates at Layer 4 (TCP/UDP/TLS).

#### Features

- Ultra-low latency
- Handles millions of requests per second
- Static IP support
- Preserves client IP address
- High-performance networking

#### Use Cases

- Gaming applications
- Real-time communication services
- High-performance applications
- Financial services systems

---

### 3. Gateway Load Balancer (GWLB)

Gateway Load Balancer simplifies deployment and scaling of virtual appliances.

#### Features

- Transparent traffic inspection
- Third-party security appliance integration
- Automatic scaling
- Centralized network security

#### Use Cases

- Firewalls
- Intrusion detection systems (IDS)
- Intrusion prevention systems (IPS)
- Deep packet inspection

---

### 4. Classic Load Balancer (CLB)

Classic Load Balancer is the legacy load balancer provided by AWS.

#### Features

- Basic Layer 4 and Layer 7 balancing
- EC2 Classic support

#### Use Cases

- Legacy applications
- Older AWS environments

> Note: AWS recommends using ALB or NLB for new deployments.

---

## Architecture

```text
                Internet
                    |
                    ▼
          Elastic Load Balancer
                    |
        ┌───────────┼───────────┐
        ▼           ▼           ▼
    EC2-1       EC2-2       EC2-3
   Healthy     Healthy     Healthy
