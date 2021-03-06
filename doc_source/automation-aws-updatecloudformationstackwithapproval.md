# AWS-UpdateCloudFormationStackWithApproval

## Description

Update Cloud Formation Stack with Approval using cloud formation template from a S3 bucket.

## Document Type

Automation

## Owner

Amazon

## Platform(s)

Windows,Linux

## Parameters

### Approvers

- **Type**: StringList
- **Description**: (Required) IAM user or user arn of approvers for the automation action

### AutomationAssumeRole

- **Type**: String
- **Description**: (Optional) The ARN of the role that allows Automation to perform the actions on your behalf.

### LambdaAssumeRole

- **Type**: String
- **Description**: (Required) The ARN of the role assumed by lambda

### SNSTopicArn

- **Type**: String
- **Description**: (Required) The SNS topic ARN used to send pending approval notification for updating CloudFormation Template. The SNS topic name must start with Automation.

### StackNameOrId

- **Type**: String
- **Description**: (Required) Name or Unique ID of the CloudFormation stack to be updated

### TemplateUrl

- **Type**: String
- **Description**: (Required) S3 bucket location of updated CloudFormation Template (e.g. https://s3.amazonaws.com/example/updated.template)

## Examples

### Start the automation

```json
aws ssm start-automation-execution --document-name AWS-UpdateCloudFormationStackWithApproval --parameters 'TODO'
```

### Retrieve the execution output

```json
aws ssm get-automation-execution --automation-execution-id EXECUTIONID --output text --query 'AutomationExecution.Output'
```

## Required IAM Permissions

TODO

## Document Steps

1. **aws:approve**
1. **aws:createStack**
1. **aws:invokeLambdaFunction**
1. **aws:deleteStack**

## Outputs

None
