# AWS-project

## Overview  
This project sets up a secure AWS environment to *log, monitor, and analyze security events* using AWS services such as *CloudTrail, S3, AWS Glue, Athena, and GuardDuty*.

---

## Table of Contents
1. [AWS Account Setup](#aws-account-setup)
2. [Security Configurations](#security-configurations)
   - Multi-Factor Authentication (MFA)
   - IAM User Creation
   - Setting Up a Budget
3. [Services Used](#services-used)
4. [Implementation Steps](#implementation-steps)
   - CloudTrail Logging
   - Storing Logs in S3
   - Data Processing with AWS Glue
   - Querying Logs with Athena
   - Threat Detection using GuardDuty
5. [Architecture Diagram](#architecture-diagram)
6. [Next Steps](#next-steps)

---

## AWS Account Setup

1. *Create an AWS Account*  
   - Go to [AWS Console](https://aws.amazon.com/).
   - Sign up and verify your account.

2. *Enable Multi-Factor Authentication (MFA)*  
   - Navigate to *IAM > Users > Security Credentials*.
   - Click *Manage MFA* and set up a virtual MFA device.

3. *Create IAM Users and Roles*  
   - Create a *least-privilege IAM user* with permissions:  
     - AmazonS3ReadOnlyAccess
     - AWSCloudTrailReadOnlyAccess
     - AthenaFullAccess

4. *Set Up AWS Budgets*  
   - Go to *Billing > Budgets*.
   - Set a monthly budget with alerts.

---

## Services Used  

| *Service*       | *Purpose* |
|-------------------|------------|
| *Amazon S3*     | Stores security logs. |
| *AWS CloudTrail* | Tracks API activity across AWS. |
| *AWS Glue*      | Catalogs and prepares log data. |
| *Amazon Athena* | Queries logs stored in S3. |
| *Amazon GuardDuty* | Detects security threats. |

---

## Implementation Steps  

### 1. CloudTrail Logging  
- Open *AWS CloudTrail > Create a new trail*.
- Enable logging for *All AWS Regions*.
- Choose an *S3 bucket* for log storage.

### 2. Storing Logs in S3  
- Create an *S3 Bucket* (security-logs-bucket).
- Set bucket permissions for CloudTrail.
- Enable *Server-Side Encryption (SSE-S3)*.

### 3. Data Processing with AWS Glue  
- Open *AWS Glue > Create a Crawler*.
- Select *S3 bucket* as the data source.
- Run the crawler to create a database.

### 4. Querying Logs with Athena  
- Open *Athena > Query Editor*.
- Create a database:
  ```sql
  CREATE DATABASE security_logs;
### 5.   
  
