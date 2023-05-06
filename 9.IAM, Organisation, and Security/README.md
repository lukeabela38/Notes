# AWS Identity and Access Management

1. Securely manage AWS resources and services
2. Root user
   1. created when account starts
   2. Full access to all account resources and services
   3. Avoid root user for daily tasks
   4. Used to create IAM with permissions to create other users

## IAM User

- Entity which interacts with AWS Resources and Services
- Consists of credentials and name
- By default has no permissions
- Recommended to create IAM user for each individual

## IAM Policies

- documents which allow or deny permissions to resources or services

## IAM groups

- Documents which allow or deny permissions to resources or services

## IAM Role

- Temporary Access to service or resource
- IAM role, user/service/application must have permission to switch roles

## Multi Factor Authentication

- Extra Layer for security

## AWS Cognito

- Authentication, authorisation and user management for web and mobile applications.
  - Use user pools or identity pools
  - User Pools: Identity tools provide AWS credentials to grant user access to other AWS services. Example of a user pool is Amazon Cognito
  - Identity Pools -> obtain temporary AWS credentials to access AWS service, allows support of anonymous users.
  - 
## AWS Organisations

- Container for AWS Accounts
- Comes with organisational Root user
- Allows management of permissions of organisational accounts
- Permissions in organisations are controlled by service control policies (SCPs), which allow you to restrict AWS resources and services for each account

Organisational units:
- Groups of accounts in the AWS organisation
- Used to manage accounts with the SAML or similar permissions more easily

## AWS KMS - Key Management Service

- Ensure app security with cryptographic keys
- A sequence of characters that may be used to encrypt or decrypt data

## AWS X-Ray

Helps debug and analyse microservices applications with request tracing to find the root cause of performance and issues
## AWS Cloud Compliance

- AWS Artifact
  - Service which provides access to compliance reports and AWS Security on Demand
  - Consists of AWS artifact reports and AWS artifact agreements (about the use of certain types of information)

## AWS Inspector

- Improve Application Security and Compliance
- Checks application for software versions and other vulnerabilities
- Creates a report of all security issues and solutions recommended for your app

## Trusted Advisor

- Web based, real time recommendation service
- Checks the account and compares findings to:
  - cost optimisation
  - performance
  - security
  - fault tolerance
  - service limits
- Trusted Advisor will then return the recommended actions

## AWS Control Tower

AWS Control Tower provides a single location to set up multi-account environments, and govern your AWS workloads with rules for secuity, operations, and internal compliance.

## AWS STS

Security token service - create and provide trusted users with temporary security credentials that can control access to your AWS resources. 

## AWS SSO

Single sign on is a service that makes it easy to centrally manage SSO access to multiple AWS accounts and business applications.

## AWS Backup

Centralised backup service that makes it easy and cost effective to backup application data across Cloud Services, helping to meet business and regulatory backup compliance requirements. AWS Backup makes protecting your AWS storage volumes, databases, and file systems simple by providing a central place to configure and audit resources.