# AWS-ASGEnterStandby

## Description

Change the Standby state of an EC2 instance in an autoscaling group

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
- **Description**: (Required) ID of EC2 Instance to change standby state for within ASG

### LambdaRoleArn

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Lambda created by Automation to perform the actions on your behalf. If not specified a transient role will be created to execute the Lambda function.

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-ASGEnterStandby --parameters 'TODO'
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

None
