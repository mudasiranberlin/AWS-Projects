# Amazon DynamoDB

## Overview

Amazon DynamoDB is a fully managed NoSQL database service provided by Amazon Web Services (AWS). It offers fast, predictable performance with seamless scalability and is designed for applications requiring low-latency data access at any scale. DynamoDB eliminates the need to manage database servers while providing automatic replication, backup, and high availability.

## Features

- Fully managed NoSQL database
- Automatic scaling
- High availability and durability
- Single-digit millisecond latency
- On-demand and provisioned capacity modes
- Point-in-Time Recovery (PITR)
- Global Tables for multi-region replication
- Built-in encryption and IAM integration
- DynamoDB Streams for event-driven applications

## Query vs Scan

- **Query** retrieves items using the partition key and is efficient.
- **Scan** reads every item in the table and should be avoided for large datasets due to higher latency and cost.

## Capacity Modes

### On-Demand

- Automatically handles traffic
- No capacity planning required
- Pay only for requests made

### Provisioned

- Specify read and write capacity
- Supports Auto Scaling
- Cost-effective for predictable workloads

## Security

DynamoDB provides:

- IAM-based access control
- Encryption at rest using AWS KMS
- TLS encryption for data in transit
- VPC endpoints for secure network access

## Backup and Recovery

DynamoDB supports:

- Point-in-Time Recovery (PITR)
- On-demand backups
- Table restoration

## Monitoring

Use Amazon CloudWatch to monitor:

- Read and write capacity usage
- Request latency
- Throttled requests
- Error rates

## Best Practices

- Design tables around application access patterns.
- Choose partition keys that distribute traffic evenly.
- Use `Query` instead of `Scan` whenever possible.
- Enable Auto Scaling or use On-Demand mode for variable workloads.
- Use secondary indexes only when required.
- Enable backups and monitoring.
- Apply the principle of least privilege using IAM policies.

## Common Use Cases

- User profiles
- Shopping carts
- Session management
- IoT applications
- Gaming leaderboards
- Serverless applications
- E-commerce systems
- Real-time analytics



## License

Author Mudasir Ahmad // @ Anberlin
