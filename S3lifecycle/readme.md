# S3 Bucket Lifecycle

## Overview

This project uses an Amazon S3 lifecycle policy to automatically manage objects in the bucket.

## What It Does

* Moves old files to a lower-cost storage class.
* Deletes files after a set number of days.
* Removes incomplete multipart uploads.

## Benefits

* Saves storage costs.
* Automates file management.
* Keeps the bucket clean.

## How to Verify

Run the following command to check the lifecycle configuration:

```bash
aws s3api get-bucket-lifecycle-configuration --bucket <bucket-name>
```
Author Mudasir Ahmad // @anberlin
