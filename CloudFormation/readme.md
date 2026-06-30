# AWS CloudFormation - Simple EC2 Instance

This project creates a simple Amazon EC2 instance using AWS CloudFormation.

## Prerequisites

Before you begin, make sure you have:

- An AWS account
- AWS Management Console access
- A valid AMI ID for your AWS region

## CloudFormation Template

Create a file named `template.yaml` and add the following code:

```yaml
Resources:
  SimpleEC2Instance:
    Type: "AWS::EC2::Instance"
    Properties:
      InstanceType: t3.micro
      ImageId: "Paste your AMI ID here" # Get the AMI ID for your AWS region (see AMI page or screenshots)
      Tags:
        - Key: Name
          Value: MySimpleInstance
```

## How to Get the AMI ID

1. Sign in to the AWS Management Console.
2. Open the **EC2** service.
3. Click **AMIs (Amazon Machine Images)** from the left menu.
4. Copy the AMI ID for your preferred operating system and region.
5. Replace:

```yaml
ImageId: "Paste your AMI ID here"
```

with your copied AMI ID, for example:

```yaml
ImageId: "ami-0123456789abcdef0"
```

## Deploy the Stack

1. Open the **CloudFormation** service.
2. Click **Create Stack**.
3. Choose **With new resources (standard)**.
4. Upload your `template.yaml` file.
5. Enter a stack name.
6. Click **Next** until you reach **Submit**.
7. Wait for the stack status to become **CREATE_COMPLETE**.

## Verify

- Open the **EC2 Console**.
- You should see an EC2 instance named:

```
MySimpleInstance
```

## Clean Up

To avoid AWS charges:

1. Open **CloudFormation**.
2. Select your stack.
3. Click **Delete**.
4. Wait until the stack is deleted.

## Project Structure

```
.
├── template.yaml
└── README.md
```

## Notes

- Replace the AMI ID with one that matches your AWS region.
- The template uses a **t3.micro** instance type.
- Deleting the CloudFormation stack will also delete the EC2 instance.

## Author

Created as a simple AWS CloudFormation learning project.

Mudasir Ahmad // @Anberlin
