# Amazon S3 Replication (CRR/SRR)

This project demonstrates how to configure **Amazon S3 Replication** to automatically copy objects from one S3 bucket to another. Any new file uploaded to the source bucket is automatically replicated to the destination bucket.

---

## 📖 Overview

In this project, you will learn how to:

- Create two Amazon S3 buckets
- Enable Bucket Versioning
- Configure an S3 Replication Rule
- Create the required IAM role
- Replicate existing objects
- Automatically replicate newly uploaded objects

---

## 🛠️ AWS Services Used

- Amazon S3
- S3 Bucket Versioning
- S3 Replication (SRR/CRR)
- AWS IAM

---

## 📋 Prerequisites

Before you begin, ensure you have:

- An AWS Account
- Permission to create S3 buckets
- Permission to create IAM roles

---

# Step 1: Create the Source Bucket

1. Open the **AWS Management Console**.
2. Navigate to **Amazon S3**.
3. Click **Create bucket**.
4. Enter the bucket name.

Example:

```text
anberlin
```

5. Choose your preferred AWS Region.
6. Enable **Bucket Versioning**.
7. Click **Create bucket**.

> **Note:** Bucket Versioning is required for S3 Replication.

---

# Step 2: Upload Files

Open the source bucket and upload a few files.

Example files:

- image.jpg
- document.pdf
- notes.txt

---

# Step 3: Create the Replica Bucket

Create another bucket.

Example:

```text
anberlinreplica
```

You can create the replica bucket in:

- The same AWS Region (Same-Region Replication - SRR)
- A different AWS Region (Cross-Region Replication - CRR)

Enable **Bucket Versioning**, then click **Create bucket**.

---

# Step 4: Configure S3 Replication

Open the source bucket:

```
anberlin
```

Navigate to:

**Management → Create replication rule**

### Configure the Replication Rule

**Rule Name**

```
ReplicationRule
```

### Source

Select:

- Apply to all objects in the bucket

### Destination

Select:

- Destination bucket
- Choose:

```
anberlinreplica
```

### IAM Role

Select:

- Create new IAM Role

Finally, click:

**Create replication rule**

---

# Step 5: Replicate Existing Objects

AWS will ask whether you want to replicate existing objects.

Select:

```
Yes
```

This copies all existing files from the source bucket to the replica bucket.

---

# Step 6: Test Replication

Upload a new file to:

```
anberlin
```

Example:

```
photo.png
```

After a few moments, Amazon S3 automatically replicates the file to:

```
anberlinreplica
```

---

## 🏗️ Architecture

```text
              Upload File
                   │
                   ▼
      +----------------------+
      |      anberlin        |
      |    Source Bucket     |
      +----------------------+
                   │
          Replication Rule
                   │
                   ▼
      +----------------------+
      |   anberlinreplica    |
      |    Replica Bucket    |
      +----------------------+
```

---

## ✅ Verification

1. Open the source bucket.
2. Upload a new file.
3. Open the replica bucket.
4. Verify the uploaded file appears automatically.
5. Check object versions if Versioning is enabled.

---

## 📚 Key Points

- Bucket Versioning must be enabled on both buckets.
- Replication supports:
  - Same-Region Replication (SRR)
  - Cross-Region Replication (CRR)
- AWS automatically creates the required IAM role.
- Existing objects can also be replicated.
- Any new object uploaded to the source bucket is automatically copied to the replica bucket.

---

## 🎯 Result

After completing this project, you will have:

- ✅ Created a source S3 bucket
- ✅ Created a replica S3 bucket
- ✅ Enabled Bucket Versioning
- ✅ Configured S3 Replication
- ✅ Replicated existing objects
- ✅ Automatically replicated newly uploaded files

---

## 👨‍💻 Author

**Mudasir Ahmad**

GitHub: https://github.com/mudasiranberlin

---

⭐ If you found this project helpful, don't forget to **Star** the repository!


# Create first s3 bucket (anberlin) and put some data there and then 
# create new bucket for replica (anberlinreplica)
Name of the bucket 
you can create n the same region or different 
Bucket Versioning enalble becuse want to check the versions 
now click on create bucket

# now go to original beucket where is the orignial data

click on management 

create relication rules 

name of rule 

Source bucket 
apply to all objects depends on which one u choose i choosse this one 

destination

select your replication bucket 

I AM create new role 

click Create replication rule

get popup replace existing object

means copy all data present in the bucket to your replica or not 

i wil select yes

now when u upload any new file in the s3 bucker (anberlin) and it will copy automatically to (anberlinreplica)
