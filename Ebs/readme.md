# Amazon EBS (Elastic Block Store)

## Overview

Amazon Elastic Block Store (EBS) is a block-level storage service designed for use with Amazon EC2 instances. It provides persistent storage volumes that can be attached to EC2 instances and used like physical hard drives.

## Features

- Persistent block storage for EC2 instances
- High availability and durability
- Snapshot support for backups
- Encryption at rest and in transit
- Scalable storage capacity
- Multiple volume types optimized for different workloads

## EBS Volume Types

| Volume Type | Description | Use Case |
|------------|-------------|----------|
| gp3 | General Purpose SSD | Most applications |
| gp2 | Previous generation SSD | Legacy workloads |
| io2 | Provisioned IOPS SSD | Critical databases |
| io1 | Provisioned IOPS SSD | High-performance workloads |
| st1 | Throughput Optimized HDD | Big data, log processing |
| sc1 | Cold HDD | Infrequently accessed data |

## Prerequisites

- AWS Account
- IAM permissions to manage EC2 and EBS resources

## Create and manage EBS volumes
## Attach and detach volumes from EC2 instances
## Delete Volumes
## Mount and UnMount
Author:  Mudasir Ahmad    /@anberlin
