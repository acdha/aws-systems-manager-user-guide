# AWS-DisableS3BucketPublicReadWrite

## Description

Disable S3-Bucket's public WriteRead access via private ACL

## Document Type

Automation

## Owner

Amazon

## Platform(s)

Windows,Linux

## Parameters

### AutomationAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Automation to perform the actions on your behalf.

### S3BucketName

- **Type**: String
- **Description**: (Required) S3 Bucket subject to access restriction

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-DisableS3BucketPublicReadWrite --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:executeAwsApi**

## Outputs

None
