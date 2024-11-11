# AWS ETL CSV Transformation Project

## Overview

This project demonstrates how to use AWS Lambda to build an ETL pipeline that reads CSV data from an S3 bucket, transforms the data, and uploads the result to another S3 bucket.

The transformation involves adding a new column `amount_spent_in_usd` based on a conversion rate of 0.85.

## Architecture

- **Amazon S3**: Stores input and output CSV files.
- **AWS Lambda**: Performs data transformations.
- **IAM Role**: Grants permissions for Lambda to access S3 buckets.

## Data Flow

1. A CSV file is uploaded to the `input-bucket`.
2. An event notification triggers the AWS Lambda function.
3. The Lambda function reads the file, transforms the data, and uploads it to the `output-bucket`.

## Lambda Function

The Lambda function performs the following tasks:
- Reads the input CSV file from S3.
- Transforms the data by adding a new column (`amount_spent_in_usd`).
- Writes the transformed data back to S3.

## Testing

To test the system:
1. Upload a sample CSV file to the `input-bucket`.
2. The Lambda function processes the data and uploads the transformed file to the `output-bucket`.

### Sample Input CSV:

```csv
customer_id,first_name,last_name,amount_spent
1,John,Doe,250
2,Jane,Smith,300
3,Mike,Johnson,150

