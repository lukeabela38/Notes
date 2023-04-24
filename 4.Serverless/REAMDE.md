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