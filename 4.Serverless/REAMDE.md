# Serverless

- Do not think about servers, no server management as opposed to EC2 Config
- Suitable for Scaling
- Providing backend services on an as-used basis
- Write/deploy code without infrastructure
- Function as a Service (FaaS)
- Capacity provisioning 
- Automatic Scaling, built in high availability, pay for value billing model

## Lambda

- Serverless Compute Service
- Event driven Compute Service
- Run code without managing servers
- Pay for used compute time based on 100ms internals and number of times your code is triggered
- Used to build, deploy, monitor and maintain apps
- Monitor through Cloudwatch
- Increase performance by increasing RAM
- Used for real time data and file processing, and stream processing
- Standard Lambda timeout is 15 minutes, or 900 seconds
- Lambda Edge - cloudfront feature, run code closer to users
- Lambda Custom Authorisation:
  - Serverless Function to authorise access to APIs
  - Lambda authoriser uses bearer authorisation such as SAML or OAuth
  - Lambda returns an IAM policy for the user when invocated
## Containers

- Used to deploy and manage applications in the cloud
- Package code in a single object
- Container isolates code and removes dependencies on other components, allowing the code to run in isolation.
- Design for scale when using containers, there could be 10s of hosts with 100s of containers

## ECS - Elastic Container Service

- Fully managed container orchestratuon service which simplifies your deployment, management, and scaling of containerised applications e.g. supports Docker, which is a platform that helps you build, test, and deploy applications.

## EKS - Elastic Kubernetes Service

- Managed Service allowing to run Kubernetes on AWS
- Built for scaling with Kubernetes

### Kubernetes 
- Open source software
- Deploy and manage containerised applications

EKS is used to run and scale Kubernetes on apps in the cloud and on premsises. Deploy applications via cloud, with your infrastructure, with your tools.

## Fargate

- Deploy and manage applications with Fargate managing the infrastructure
- serverless system, with pay as you go pricing.

## Edge Locations

A data center us used to deliver content quickly to your users. It uses a service callec Cloudfront, which caches copies of your content, resulting in fast delivery of your content.

A cache is a piece of software used to deliver content faster and cheaper. It is a fast storage that copies and stores parts of data. The data is stored in hardware that can deliver content quickly - RAM (random access memory). The cache works by saving subsets of the data, making it available.

The content is delivered quicker as it is no longer requested from the primary location, but rather an edge location.  Once someone requests the data, it is sored and copied at the edge location.

## Elastic Beanstalk

A web infrastructure management service which handles deployment and scaling for web applciations and services. Helps automatically manage AWS Services, Setup, Configuration, and scaling, and provisioning: can be used in conjunction for EC2, S3, RDS, DynamoDB, and SimpleDB

- provide code and configuration settings
- Deploy code and necessary resources to perform the following tasks:
  - adjust capacity,
  - load balancing,
  - automatic scaling,
  - application health monitoring

## Cloudfront (CDN)

- Content Delivery Network
- Low Latency and High transfer Speeds
- Improves Application performance
- Cache content at edge locations
- Works with AWS Shield for DDoS mitigation

## Cloudfront Origin

- Origin is location where content is stored, and from which cloudfront gets content to servers to customers
- Origin types may include S3, EC2, ALB, HTTP Backend

## Cloudfront Geo Restrictions

- Restrict access to your content based on user location
- Configure whitelist/blacklist
- Use WAF to monitor and restrict HTTP and HTTP Requests
- Cloudfront for static content available vs S3 Cross region replication for dynamic conent that needs to be available at low latency in few regions

## Cloudfront Signed URL/Signed Cookies

- Premium Content to paid users
  - Valid IP ranges
  - URL expiration
  - Trusted Signer (AWS accounts that can create signed URLs):
    - Signed URLs: access to individual files
    - Signed Cookie: reuse same cookie for multiple files

## Cloudfront Signed URL

- Control Access to a path, so that any origin is supported
- USes account wide key pair, which only root user can manage
- Set parameteres such as expiration, IP, and path

## Serverless Application Model (SAM)

- Serverless application Model
  - use SAM to define serverless applications
  - Framework for deploying and deploying serverless applications
  - Single Deployment Configuration:
    - Easy to organise related components and resources operate on a single track
    - run Lambda, API Gateway, DynamoDB
    - Local Debugging and Testing

## Step Functions
- build serverless workflows to orchestrate lambda functions
- Represent JSON state machine
- Use step functions over simple workflow except for when:
  - external signal is required
  - Need child process to return value to parent process


## AWS Proton

Deploy serverless or container based application with efficiency, consistency, and control. Define infrastructure standards and effective continous delivery pipelines. It is commonly used by developers to manage architecture.

