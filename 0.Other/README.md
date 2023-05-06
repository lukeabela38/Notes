# Miscellaneous

## Cloudformation

- Infrastructure Service
- Creates templates to describe the AWS services you want
- Handles the configuration and privisioning of the resources described in the template
- It makes it easier because you do not have to configre the resources individually
- Cloudformation helpts to handle the dependecies between resources
  
## Kinesis 

- Collect, process, analyse streaming data real time. 

1. Firehouse: Load Streams into stores near real time
2. Analytics: Analyse streams with SQL or Apache.

## EMR

Amazon EMR (elasticmap reduce) is a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark, on AWS to process and analyse vast amounts of data. Used to process data for analytics purposes and business intelligence. EMR is specifically used for big data processing.
## Glue

- Serverless data inetgration
- ETL (extract, transform, load) service
- Prepare and transform data for analytics
- Glue Data Catalog
  - metadata of all data in the aws account
- Serverless
- Automatically generates code to run loading and data transformations

## Innovation

- Sagemaker - machine learning environment
- LEX - voice/text chatbots
- Transcibe - speech to text
- Comprehend - discover text patterns
- Amazon Fraud Detection
## AWS Global Accelerator 

- Leverage AWS to minimise latency
- Unicast IP: single host, one server holds one IP
- Anycast IP: all servers holds the same IP address, client routed to the nearest one
  - keep packet loss, jitter, and latency consistently low
- For Elastic IP, Ec2, ALB, NLB
- Performs health checks for failover and disaster Recovery

## API Gateway

- managed service to create, publish, maintain, monitor, and secure APIs at any scale
- 1000s for API calls
- Create API keys
- Handle request throttling
- Restful or Websocket
- Efficient API development
- Performance at scale
- Cost savings
- Monitor using Cloudwatch
- Edge optimised API endpoints
- Regional API Endpoints:
  - For use in same region
  - Custom domain name that is specific to where API is deployed
  - Manually combine with Cloudfront
- Private API Endpoints:
  - access via VPC

- Control API using API key or AWS IAM for internal APIs
  - IAM credentials in headers

## Application Discovery Service

- Collect information about on premises servers
- Help plan migration -> track utilisation and dependency mappings
- Track migration using AWS Migration Hub

## AWS Server Migration Service

- Incremental Replication
- Migration On premises servers to AWS Cloud
- Ongoing or incremental application

## AWS Shared Responsibility Model

AWS manages cloud security and all infrastructure layers:
- data centers
- hardware and software
- virtualisation
- networking

Customer is responsible for the security of their work in the cloud including:
- services,
- software,
- data access

## Cloudwatch

- Web based service to monitor resources
- Configure service to monitor and set alarms based on metrics

- ALarms triggered at user defined thresholds
- Gain system wide visibility into resource utilisation, app performance, and operational health
- Customisable dashboards
- Cloudwatch metrics: Kept for 15 months - metrics belong to namespace, and up to 10 dimensions per metric
- Use the cloudwatch agent or PutMetricData API action to publish metrics to cloudwatch
- updates with up to per second frequency
- With free tier for EC2 you can monitor:
  - CPU Load
  - Disk I/O
  - Network I/O Metrics
  - NO memory related metrics
  - By default sends in 5 minute intervals

## Cloudtrial

- Log actions inside AWS environment and record API calls on your account e.g. Identity, Time, IP address
- Cloudtrial can be used to make events to understand what has happened, by filderting for who, when, and how
- Cloudtrial insights allow you to detect unusual API activities on your account by automation

## AWS Config

- Assess, audit, evaluate AWS configurations of resources
- Evaluate configurations against desired configurations
- Store configuration data in S3
- This is a per region service
- Use rules to evaluate
- Cost is at $2 per active rule per region per month

## Marketplace

- digital catalog to list and sell software
- explore, test, and purchase software that runs on AWS
- Pricing, support, options, customer reviews

## Transfer for SFTP

AWS transfer for STFP enables you to move file transfer workloads that use the secure shell file transfer protocol to AWS without needing to modify your applications or modify any servers.