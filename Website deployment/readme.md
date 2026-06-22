# Hosting a Website on AWS EC2 with Apache HTTP Server

This guide explains how to launch an AWS EC2 instance, install Apache (httpd), and host a simple website.

---

## Prerequisites

- AWS Account
- EC2 Key Pair
- Basic knowledge of Linux commands
- Security Group configured for HTTP and SSH access

---

## Step 1: Launch an EC2 Instance

1. Open the AWS Management Console.
2. Navigate to **EC2**.
3. Click **Launch Instance**.
4. Choose an Amazon Linux AMI.
5. Select the desired instance type.
6. Create or select an existing key pair.
7. Configure the Security Group:
   - Allow **SSH (Port 22)** from your IP.
   - Allow **HTTP (Port 80)** from Anywhere.
   - Allow **HTTPS (Port 443)** if required.
8. Review and launch the instance.

---

## Step 2: Connect to the EC2 Instance

Use SSH to connect:

```bash
ssh -i your-key.pem ec2-user@<PUBLIC-IP>
```

---

## Step 3: Switch to Root User

```bash
sudo su -
```

---

## Step 4: Install Apache HTTP Server

For Amazon Linux:

```bash
yum install httpd -y
```

Verify installation:

```bash
httpd -v
```

---

## Step 5: Start Apache Service

Start the web server:

```bash
systemctl start httpd
```

Enable Apache to start automatically on reboot:

```bash
systemctl enable httpd
```

Check service status:

```bash
systemctl status httpd
```

---

## Step 6: Navigate to the Web Root Directory

Apache serves files from:

```bash
cd /var/www/html
```

---

## Step 7: Create Your Website

Create an HTML file:

```bash
nano index.html
```

Example:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My EC2 Website</title>
</head>
<body>
    <h1>Welcome to My Website Hosted on AWS EC2!</h1>
</body>
</html>
```

Save and exit the file.

---

## Step 8: Access the Website

Open a browser and visit:

```text
http://<PUBLIC-IP>
```

You should see your website running successfully.

---

# Alternative Method: User Data Script

Instead of installing everything manually, you can use a User Data script while launching the EC2 instance.

Example:

```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd

echo "<h1>Website Deployed Using User Data</h1>" > /var/www/html/index.html
```

This automatically installs Apache and creates a sample webpage during instance startup.

---

## Useful Commands

### Restart Apache

```bash
systemctl restart httpd
```

### Stop Apache

```bash
systemctl stop httpd
```

### Check Apache Status

```bash
systemctl status httpd
```

### View Web Files

```bash
ls -la /var/www/html
```

---

## Security Group Rules

| Type | Port | Purpose |
|--------|------|---------|
| SSH | 22 | Remote Access |
| HTTP | 80 | Website Access |
| HTTPS | 443 | Secure Website Access |

---

## Project Workflow

1. Launch EC2 Instance
2. Create/Select Key Pair
3. Configure Security Group
4. Connect via SSH
5. Switch to Root User
6. Install Apache (httpd)
7. Start Apache Service
8. Create Website Files
9. Access Website via Public IP

---

## Author
Mudasir Ahmad

AWS EC2 Website Hosting 
