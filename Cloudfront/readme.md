# AWS CloudFront Service

## Overview

This project demonstrates how to configure and deploy Amazon CloudFront as a Content Delivery Network (CDN) to securely and efficiently deliver web content with low latency and high transfer speeds.

Amazon CloudFront caches content at edge locations worldwide, reducing load on the origin server while improving application performance and availability.

---

## Features

- Global content delivery using AWS edge locations
- HTTPS support with SSL/TLS certificates
- Integration with Amazon S3, EC2, Application Load Balancer, or custom origins
- Origin Access Control (OAC) / Origin Access Identity (OAI) support
- Cache behavior configuration
- Custom domain (CNAME) support
- AWS WAF integration
- Access logging
- Automatic content compression
- IPv6 support


## Project Overview

This project demonstrates how to host a static website on Amazon S3 and deliver it using Amazon CloudFront.

## Steps

### 1. Create an S3 Bucket
- Create an Amazon S3 bucket.
- Upload your website files (HTML, CSS, JavaScript, images, etc.) to the bucket.

### 2. Create a CloudFront Distribution
- Open the AWS Management Console.
- Go to **CloudFront** and click **Create Distribution**.

### 3. General Settings
- **Distribution name:** `anberlin`
- Leave all other settings as their default values.
- Click **Next**.

### 4. Origin Settings
- **Origin type:** Amazon S3
- **S3 origin:** Select your S3 bucket.
- Leave the remaining settings as default.
- Click **Next**.

### 5. Security Settings
Under **Web Application Firewall (WAF)**, select:
- **Do not enable security protections**

Click **Create Distribution**.

### 6. Configure the Default Root Object
After the distribution is created:
- Open the distribution.
- Go to **General** → **Edit**.
- Set the **Default root object** to `index.html`.
- Leave all other settings unchanged.
- Click **Save Changes**.

### 7. Configure the Origin
- Open the **Origins** tab.
- Select your origin and click **Edit**.
- Configure the following:
  - **Origin domain:** Your S3 bucket
  - **Origin path:** `index.html`
  - **Origin access:** **Origin access control settings (recommended)**
  - **Origin access control:** Create a new Origin Access Control (OAC)

CloudFront will display a bucket policy. Copy this policy.

### 8. Update the S3 Bucket Policy
- Open your S3 bucket.
- Go to **Permissions** → **Bucket policy**.
- Paste the policy provided by CloudFront.
- Save the bucket policy.
- Return to CloudFront and save the origin changes.

### 9. Now you can copy the Distribution domain name and open in the browser

## Result

Once the distribution finishes deploying, access your website using the CloudFront distribution domain. Your website is now securely delivered through Amazon CloudFront with Origin Access Control enabled.

Author 

Mudasir Ahmad /@Anberlin
