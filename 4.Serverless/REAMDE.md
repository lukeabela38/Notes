# Serverless

- Do not think about servers, no server management as opposed to EC2 Config
- Suitable for Scaling

## Lambda

- Serverless Compute Service
- Run code without managing servers
- Pay for used compute time
- Used to build, deploy, monitor and maintain apps

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

