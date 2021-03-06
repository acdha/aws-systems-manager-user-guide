# AWS-DeleteCloudFormationStack

## Description

Delete CloudFormation Stack

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

### StackNameOrId

- **Type**: String
- **Description**: (Required) Name or Unique ID of the CloudFormation stack to be deleted

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-DeleteCloudFormationStack --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:deleteStack**

## Outputs

None
