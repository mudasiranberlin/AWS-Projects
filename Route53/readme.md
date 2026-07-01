# AWS Route 53 Configuration

This project contains the configuration and infrastructure code for managing DNS records using Amazon Route 53.

## Overview

Amazon Route 53 is a scalable Domain Name System (DNS) web service that provides:

- Domain registration
- DNS routing
- Health checks
- Traffic management
- DNS failover

This repository manages Route 53 hosted zones and DNS records for the project.

## Prerequisites

Before deploying, ensure you have:

- AWS Account
- Domain
- Route 53 Hosted Zone

## Configuration

Update the following values before deployment:

- Hosted Zone ID
- Domain Name
- Record Names
- Record Values
- TTL
- Routing Policy (if applicable)

Example:

```text
Domain: example.com
Hosted Zone ID: Z123456789ABCDEF
TTL: 300
```

## Health Checks

Route 53 health checks can be configured to monitor application endpoints and automatically route traffic based on endpoint availability.

Example health check:

- Protocol: HTTPS
- Port: 443
- Path: `/health`
- Interval: 30 seconds

## Routing Policies

Supported routing policies include:

- Simple
- Weighted
- Latency
- Failover
- Geolocation
- Geoproximity
- Multi-Value Answer

## Security

- Follow the principle of least privilege for IAM roles.
- Restrict access to Route 53 resources.
- Store AWS credentials securely.
- Enable logging and monitoring where applicable.

## Verification

Verify DNS records:

```bash
dig example.com

nslookup example.com
```
                  
## Troubleshooting

Common issues include:

- Incorrect Hosted Zone ID
- Missing IAM permissions
- DNS propagation delays
- Incorrect record values
- Domain not delegated to Route 53 name servers

## References

- AWS Route 53 Documentation
- AWS CLI Documentation
- Terraform AWS Provider Documentation

## License

Mudasir Ahmad @ANberlin
