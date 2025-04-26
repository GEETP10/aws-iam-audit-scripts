# aws-iam-audit-scripts
# AWS IAM Audit Scripts

This project contains simple Python scripts to automate AWS IAM user, role, and policy audits.

## Features
- List all IAM users with creation dates
- Identify unused IAM roles
- Check for overly permissive IAM policies

## Technologies
- Python
- Boto3 AWS SDK

## Sample Script
```python
import boto3

def list_iam_users():
    iam = boto3.client('iam')
    users = iam.list_users()
    for user in users['Users']:
        print(f"User: {user['UserName']} Created: {user['CreateDate']}")

if __name__ == "__main__":
    list_iam_users()
