# AWS-PatchInstanceWithRollback

## Description

Brings EC2 Instance into compliance with standing Baseline; rolls back root Volume on failure

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

### InstanceId

- **Type**: String
- **Description**: (Required) EC2 InstanceId to which we apply the patch-baseline

### LambdaAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Lambda created by Automation to perform the actions on your behalf. If not specified a transient role will be created to execute the Lambda function.

### ReportS3Bucket

- **Type**: String
- **Description**: (Optional) S3 Bucket destination for the Compliance Report generated during process

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-PatchInstanceWithRollback --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:createStack**
1. **aws:invokeLambdaFunction**
1. **aws:executeAutomation**
1. **aws:runCommand**
1. **aws:invokeLambdaFunction**
1. **aws:invokeLambdaFunction**
1. **aws:invokeLambdaFunction**
1. **aws:invokeLambdaFunction**
1. **aws:invokeLambdaFunction**
1. **aws:invokeLambdaFunction**
1. **aws:deleteStack**

## Outputs

IdentifyRootVolume.Payload
PrePatchSnapshot.Output
SaveComplianceReportToS3.Payload
RestoreFromSnapshot.Payload
CheckCompliance.Payload
