# AWS Organization

## Overview

AWS Organizations helps you organize multiple AWS accounts under a single management account. It makes it easier to manage security, billing, and access across all accounts.

---

## What is AWS Organizations?

AWS Organizations is an AWS service that allows you to:

- Manage multiple AWS accounts from one place  
- Group accounts into Organizational Units (OUs)  
- Apply security and compliance policies  
- Consolidate billing across all accounts  
- Control access using Service Control Policies (SCPs)

---

## Features

- Centralized AWS account management  
- Consolidated billing  
- Organizational Units (OUs)  
- Service Control Policies (SCPs)  
- IAM Identity Center integration (optional)  
- Security best practices enforcement  
- Account isolation  
- Scalable multi-account architecture  

---

## Best Practices

- Keep the management account for administrative purposes only  
- Separate production and development accounts  
- Enable CloudTrail for all accounts  
- Use SCPs to enforce security policies  
- Enable AWS Config where required  
- Follow least-privilege IAM access  
- Enable Multi-Factor Authentication (MFA) for privileged users  

---

## Common AWS Services Used

- AWS Organizations  
- AWS IAM  
- AWS IAM Identity Center  
- AWS CloudTrail  
- AWS Config  
- Amazon CloudWatch  
- AWS Backup  

---

## Benefits

- Improved security  
- Easier account management  
- Centralized billing  
- Better compliance control  
- Resource isolation  
- Easier scalability  

---

## Getting Started

### 1. Access AWS Organizations
Go to AWS Organizations in the AWS Management Console.  
Click on **AWS Accounts** to view existing accounts.

---

### 2. Add a New AWS Account

You can add accounts in two ways:

#### Option 1: Create a new AWS account
- AWS will create a new account under your organization

#### Option 2: Invite an existing AWS account
- Enter the email address or AWS Account ID
- Add an optional message
- Send the invitation

---

### 3. Accept or Decline Invitation

To check invitations:

- Go to **AWS Organizations**
- Click on **AWS Accounts**
- Open the **Invitations** section
- Choose **Accept** or **Decline**

---

### 4. Apply Policies (SCPs)

You can control permissions using policies:

- Go to **Policies** in AWS Organizations
- Search or create a policy
- Write policy in JSON format
- Attach it to accounts or Organizational Units (OUs)

Example:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*"
    }
  ]
}
```

---

## Security

- Enable Multi-Factor Authentication (MFA)  
- Use least-privilege access  
- Regularly review IAM permissions  
- Enable AWS CloudTrail and AWS Config  
- Monitor activity using CloudWatch  

---

## Contributing

Feel free to improve this documentation by submitting a pull request.

---

## For reference
See the screenshots as well
