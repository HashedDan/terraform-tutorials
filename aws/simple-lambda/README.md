# Deploy an AWS Lambda Function

This example follows closely with HashiCorp's Lambda / API Gateway [tutorial](https://learn.hashicorp.com/terraform/aws/lambda-api-gateway).

*Note:* Parts of this example require the AWS CLI to be installed.

## Write the Lambda Function (NodeJS)

The first thing we want to do is actually write the code for we want to execute in the Lambda function. The code provided is a simple function that returns `"Hello World!"` in paragraph tags. Feel free to alter it to do whatever you wish.

## Zip the Lambda Function

Use the simple shell script (zipFunc) to zip up our Lambda function (this is required by the AWS Lambda service).

## Create an S3 Bucket and Upload the Lambda Function

This is when we will need the AWS CLI installed. If installed, run the following commands to provision an S3 bucket and upload the Lambda function zip file.

```aws s3api create-bucket --bucket=terraform-lambda-y458458487458ytrut845--region=us-west-2```

```aws s3 cp function.zip s3://terraform-lambda-y458458487458ytrut845/v1.0.0/function.zip```

*You are welcome to change the bucket / zip file names as you see fit, but you will need to make the same changes in `main.tf`*

## Understanding Our Terraform Configuration