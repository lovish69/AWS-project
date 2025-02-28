# AWS-project

## Overview  
This documentation covers the entire process of setting up an AWS account, enabling security measures, managing budgets, and implementing services such as Athena, S3, CloudTrail, GuardDuty, and AWS Glue for security analysis.

[Uploading saws.drawio…]()


---

## Table of Contents
1. [AWS Account Setup](#aws-account-setup)
2. [Security Configurations](#security-configurations)
   - Multi-Factor Authentication (MFA)
   - IAM User Creation
   - Setting Up a Budget
3. [Services Used](#services-used)
   - S3 (Simple Storage Service)
   - CloudTrail
   - AWS Glue
   - Athena
   - GuardDuty
4. [Implementation Steps](#implementation-steps)
   - Setting Up Logging with CloudTrail
   - Storing Logs in S3
   - Processing Data with AWS Glue
   - Querying Logs Using Athena
   - Threat Detection with GuardDuty
5. [Architecture Diagram](#architecture-diagram)

---

## AWS Account Setup

1. *Create an AWS Account*  
   - Visit [AWS Console](https://aws.amazon.com/) and sign up.
   - Provide billing details and complete verification.

2. *Enable Multi-Factor Authentication (MFA)*  
   - Go to *IAM > Users > Security Credentials*.
   - Click *Manage MFA* and set up a virtual MFA device (Google Authenticator).

3. *Create IAM Users and Roles*  
   - Create an IAM user with limited permissions for daily operations.
   - Assign necessary policies (AmazonS3ReadOnlyAccess, AWSCloudTrailReadOnlyAccess, etc.).

4. *Set Up AWS Budgets*  
   - Navigate to *Billing > Budgets*.
   - Set a monthly budget and configure notifications for cost monitoring.

---

## Services Used  

1. *Amazon S3*  
   - Stores CloudTrail logs securely.  

2. *AWS CloudTrail*  
   - Records all API activity within AWS for security auditing.

3. *AWS Glue*  
   - Processes and catalogs log data.

4. *Amazon Athena*  
   - Queries logs from S3 using SQL.

5. *Amazon GuardDuty*  
   - Detects security threats and anomalies.

---

## Implementation Steps  

### 1. Setting Up Logging with CloudTrail  
- Go to *CloudTrail > Create a new trail*.
- Enable logging for *All AWS Regions*.
- Choose an *S3 bucket* for log storage.

### 2. Storing Logs in S3  
- Create an *S3 Bucket* (aws-security-logs).
- Set permissions for CloudTrail logs.
- Enable *Server-Side Encryption (SSE-S3)*.

### 3. Processing Data with AWS Glue  
- Create a *Crawler* in AWS Glue.
- Point it to the S3 bucket storing CloudTrail logs.
- Run the crawler to create a data catalog.

### 4. Querying Logs Using Athena  
- Open *Athena > Query Editor*.
- Create a database:  
  ```sql
  CREATE DATABASE security_logs;
  ```
### 5.   
  
