# Lambda-AWS


This Terraform configuration deploys an AWS Lambda function and sets up its execution environment, including the necessary triggers and permissions. It starts by specifying the AWS provider and region (⁠ us-west-2 ⁠) and configuring the Terraform state to be stored in an S3 backend. An S3 bucket is created for storing resources, though its purpose is not explicitly tied to the Lambda in this configuration. 

An IAM role (⁠ lambda_execution_role ⁠) is defined with a policy allowing AWS Lambda to assume it, and a managed policy (⁠ AWSLambdaBasicExecutionRole ⁠) is attached to enable basic Lambda execution permissions. The Lambda function is then created using a Python 3.8 runtime, with its code specified as a ⁠ .zip ⁠ file and a handler function. 


To automate execution, a CloudWatch Event Rule is set up to trigger every 5 minutes, and a target is configured to associate the rule with the Lambda function. Lastly, a permission is added to allow the CloudWatch Events service to invoke the Lambda function. This setup ensures the Lambda function runs periodically based on the specified schedule.
