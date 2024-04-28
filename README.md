# cost-optimization-ebs
# Snapshot Management for EC2 Instances

This repository contains code and instructions for managing snapshots of Amazon Elastic Compute Cloud (EC2) instances.

## Overview

The process involves creating snapshots of EC2 instance volumes and automating the deletion of these snapshots when their associated volumes are deleted. The workflow is as follows:

1. **Create EC2 Instance**: Launch an EC2 instance and ensure that its volume is created.
2. **Take Snapshots**: Take snapshots of the volumes attached to the EC2 instance.
3. **Lambda Function**: Implement a Lambda function to delete snapshots when the associated volumes are deleted.
4. **IAM Role and Permissions**: Grant necessary permissions to the Lambda function to interact with EC2 resources.
5. **Execution and Error Handling**: Execute the code and handle any potential errors that may arise.

## Code Structure

The code is structured as follows:

1. **List Resources**: List all running instances, EBS snapshots, and volumes using Boto3.
    - For running instances: [describe_instances documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/ec2/client/describe_instances.html)
    - For EBS snapshots: [describe_snapshots documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/ec2/client/describe_snapshots.html)
    - For volumes: [describe_volumes documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/ec2/client/describe_volumes.html)

2. **Check Snapshot Attachments**: Verify if snapshots belonging to volumes are attached to running instances.

3. **Exception Handling**: Implement error handling to manage potential errors during execution.

## Usage

Follow these steps to use the code:

1. Launch an EC2 instance.
2. Take snapshots of the associated volumes.
3. Create and configure a Lambda function to delete snapshots.
4. Grant necessary permissions to the Lambda function using IAM.
5. Execute the code and handle any errors.
6. Verify that snapshots are deleted when associated volumes are deleted.

## Additional Resources

- [Error Handling and Monitoring in AWS Lambda](https://staskoltsov.medium.com/error-handling-and-monitoring-in-aws-lambda-325c0ade251a)
- [Boto3 Error Handling Guide](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/error-handling.html)

For further assistance, refer to the provided documentation and code snippets.
 
