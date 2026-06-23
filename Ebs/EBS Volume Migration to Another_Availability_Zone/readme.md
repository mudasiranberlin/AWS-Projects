# Mounting and Accessing a Secondary Amazon EBS Volume

## Overview

This guide explains how to mount and access a secondary Amazon EBS volume attached to an EC2 instance. It covers verifying the filesystem, mounting the partition, navigating the data, viewing and editing files, and safely unmounting the volume.

## Device Information

| Device           | Description                                 |
| ---------------- | ------------------------------------------- |
| `/dev/nvme1n1`   | Newly attached secondary EBS volume         |
| `/dev/nvme1n1p1` | First partition on the secondary EBS volume |

> **Note:** Device names may vary depending on the EC2 instance type and operating system. Always verify using `lsblk` before proceeding.

---

## Step 1: Verify the Filesystem

Inspect the filesystem signature of the target partition to confirm it contains a valid filesystem.

```bash
sudo file -s /dev/nvme1n1p1
```

### Example Output

```text
/dev/nvme1n1p1: Linux rev 1.0 ext4 filesystem data
```

---

## Step 2: Create a Mount Point

Create a directory that will be used as the mount location.

```bash
sudo mkdir /mnt/mybackup
```

---

## Step 3: Mount the EBS Volume

Mount the partition using the `nouuid` option.

This option is commonly required when mounting volumes restored from snapshots or cloned EBS volumes because duplicate filesystem UUIDs may exist.

```bash
sudo mount -o nouuid /dev/nvme1n1p1 /mnt/mybackup/
```

---

## Step 4: Verify the Mount

Confirm that the volume has been mounted successfully and review disk usage.

```bash
df -h
```

### Example Output

```text
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme1n1p1  100G   40G   60G  40% /mnt/mybackup
```

---

## Step 5: Navigate to the Mounted Filesystem

Move to the mount point and inspect its contents.

```bash
cd /mnt/mybackup/
ls
```

---

## Step 6: Access the User Home Directory

Navigate to the replicated EC2 user directory.

```bash
cd home/ec2-user/
ls
```

---

## Step 7: Access the Workspace Directory

Enter the target workspace directory.

```bash
cd mudasir
ls
```

---

## Step 8: View File Contents

Display the contents of the file named `muzamil`.

```bash
cat muzamil
```

---

## Step 9: Edit the File

Open the file using the Vim editor.

```bash
vi muzamil
```

### Useful Vim Commands

| Action              | Command |
| ------------------- | ------- |
| Enter Insert Mode   | `i`     |
| Save Changes        | `:w`    |
| Quit Vim            | `:q`    |
| Save and Exit       | `:wq`   |
| Exit Without Saving | `:q!`   |

---

## Step 10: Safely Unmount the Volume

Before unmounting, ensure your current working directory is not inside the mounted filesystem.

For example:

```bash
cd ~
```

Perform a lazy unmount:

```bash
sudo umount -l /mnt/mybackup
```

### Why Use `-l`?

The `-l` (lazy unmount) option detaches the filesystem immediately and cleans up references once they are no longer in use. This is helpful when processes still have open handles to the mount point.

---

## Complete Command Sequence

```bash
# Verify filesystem
sudo file -s /dev/nvme1n1p1

# Create mount point
sudo mkdir /mnt/mybackup

# Mount volume
sudo mount -o nouuid /dev/nvme1n1p1 /mnt/mybackup/

# Verify mount
df -h

# Navigate through filesystem
cd /mnt/mybackup/
ls

cd home/ec2-user/
ls

cd mudasir
ls

# View file contents
cat muzamil

# Edit file
vi muzamil

# Exit mount path before unmounting
cd ~

# Unmount volume
sudo umount -l /mnt/mybackup
```

---

## Troubleshooting

### Verify Available Disks

```bash
lsblk
```

### Display Filesystem UUIDs

```bash
sudo blkid
```

### Check Mounted Filesystems

```bash
mount | grep mybackup
```

### "Device is Busy" Error

If unmounting fails:

1. Exit all directories under `/mnt/mybackup`
2. Close any editors or shells using the mount
3. Retry the unmount command

```bash
sudo umount -l /mnt/mybackup
```

---

## Best Practices

* Always verify the correct device before mounting.
* Use `nouuid` when mounting cloned or restored EBS volumes.
* Validate mounted storage using `df -h`.
* Unmount volumes before detaching them from the EC2 instance.
* Avoid editing production data directly unless necessary.
