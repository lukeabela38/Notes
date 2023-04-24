# Introduction

## Cloud Computing 

Client - Server Model
1. Client interacts with and makes requests to a computer server.
2. Server does tasks and return information

## Deployment Models

Cloud Based Deployment:
1. Everything runs on the cloud
2. Build or move Applications to the Cloud
3. Virtual Servers, Databases, Networking Components all based in the cloud

On Premises Deployment (Private):
1. Applications run on technology fully kept on-premises

Hybrid Deployment:
1. Connect cloud resources to an on-premises infrasturcture

## Benefits of Cloud Computing

1. Cost savings, security, scalability, flexibility
2. Using Cloud means you do not have to invest in a data center, servers, etc etc ...
3. Cloud Computing is a variable expense, and hence can be managed
4. Consume more resources as you grow
5. No resources or staffing are necessary to operate the data center
6. Flexible capacity allows you to shrink or grow as required
7. Economies at Scale: Share resources with other to lower overall csosts
8. Incereased Speed, especially for research and development
9. Global reach -> deploy apps to consumers everywhere


## AWS Infrastructure

- Global Infrastructure with data centers all over the world.
- Deploy apps across the globe or to a specific location.

## AWS Regions

- different regions have different regulations, customer, proximity, service availablitiy, and pricing.
- Different regions also have different regulations due to governance, some countries do not allow sensitive data to be processed and stored abroad.
- Customer proximity - seleting a  region near your customers can help to make services faster.
- Region Specific Services:
  - Not all AWS data centers support all services and features.
  - AWS often builds new features, they must make the necessary infrastructure available in the data centers.

## Availablity Zones

- An availablitiy Zone is a single data center or a group of data centers in a region
- Data centers are typically many miles apart to reduce risk in event of disaster.

E.g. The region: eu-west-1 has zones: 
- eu-west-1a
- eu-west-1b
- eu-west-1c


## How to Interact

- AWS Management Console: Web based interface to access and manage services
- AWS Command Line Interface:
  - Save time when making API requests
  - Control Multiple services with a single tool
  - Automate actions on services with Scripts
- Software Development Kits: Eases use of AWS Services through an API
- API fitted to platform or programming language being used