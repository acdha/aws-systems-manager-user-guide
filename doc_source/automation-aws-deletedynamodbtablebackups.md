# AWS-DeleteDynamoDbTableBackups

## Description

Deletes DynamoDB table backups based on retention days 'OR' count.

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

### LambdaAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Lambda created by Automation to perform the actions on your behalf. If not specified a transient role will be created to execute the Lambda function.

### RetentionCount

- **Type**: String
- **Default**: 10
- **Description**: (Optional) The number of backups to retain for the table. If more than the specified number of backup exist, the oldest backups beyond that number are deleted. Either RetentionCount or RetentionDays can  be used, not both.

### RetentionDays

- **Type**: String
- **Description**: (Optional) The number of days to retain backups for the table. Backups older than the specified number of days are deleted. Either RetentionCount or RetentionDays can  be used, not both.

### TableName

- **Type**: String
- **Description**: (Required) Name of the DynamoDB Table.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-DeleteDynamoDbTableBackups --parameters 'TODO'
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
1. **aws:deleteStack**

## Outputs

deleteDynamoDbTableBackups.Payload
