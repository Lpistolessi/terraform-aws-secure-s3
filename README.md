# Secure S3 Bucket with Terraform

A small learning project demonstrating baseline S3 security controls using Terraform.

> **Project status:** This is a learning project and has not yet been deployed or validated against a live AWS account. Review the Terraform plan and test it in a sandbox account before using it for real resources.

## What it creates
- An S3 bucket with a configurable name
- Server-side encryption using S3-managed keys (SSE-S3)
- Bucket versioning
- All S3 Block Public Access settings enabled
- A bucket policy denying non-TLS requests

## Prerequisites
- Terraform installed
- AWS CLI configured with credentials outside this repository
- AWS permissions to create and manage S3 buckets and bucket policies

## Usage
1. Review `versions.tf` and `main.tf`.
2. Create a local `terraform.tfvars` file with a globally unique bucket name, for example:
   ```hcl
   bucket_name = "my-unique-learning-bucket-12345"
   ```
3. Run:
   ```bash
   terraform init
   terraform fmt -check
   terraform validate
   terraform plan
   terraform apply
   ```
4. When finished, remove the resources with `terraform destroy`.

## Security notes
- Never commit credentials, state files, or real `.tfvars` files.
- This is a learning example, not a complete production module.
- S3 bucket names are globally unique. Choose a name you control and review the plan before applying.
- Terraform state can contain sensitive infrastructure metadata. Store it securely if you later configure a remote backend.
