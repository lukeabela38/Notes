# AWS Messaging

## Monolithic Application

1. Architecture with Tightly Coupled Components such as databases, servers, interfaces, and more.
2. Vulnerable if any one Component fails, which may cause the whole service to go down.

## Microservices

1. Help maintain the service if any one component fails.
2. Services communicate with one another and are not tightly coupled.

These may communicate via AWS SNS - Simple Notification Service, or the AWS SQS - Simple Queue Service

## SNS

Simple Notification Service 
1. Cloud Service for delivery of mass messages, push messages to subscribers
2. Publish Subscribe Model
3. Event driven, with automated services responding to triggers.

Application to person messaging possible via SMS, mobile push, and email. Message endpoints include:

- https/http
- email/email json
- SQS
- Applications
- Lambda
- SNS

## SQS

Simple Queue Service

Exchange and store messages between software components

- service adds message to the queue
- Users pick up messages
- Once processed, message is deleted