# AWS Networking

## Virtual Private Cloud

- VPC is a service which lets you isolate AWS resources in an isolated network.
- The boundaries of which let AWS restrict network traffic.
- Allows you to include sections of AWS Cloud that you want in an isolated network.
- Resources can be organised via subnets, a section in VPC that can contain specific resources.

## Internet Gateway

- Public Traffic can be allowed to your VPC
- The internet gateway is a door between the VPC and your internet

## Virtual Private Gateway

- Access private resources within the VPC
- VPC encrypts internet traffic
- Allows encrypted traffic to enter the VPC

The Virtual private gateway allows you to create a virtual private network between the VPC and the private network, allowing traffic only from approved networks.

## Peered VPCs

VPC peering is a networking connection between two VPCs which enables you to route traffic between them using private IPv4 or IPv6 addresses.

- Helps facilitate data transfer.
- No charge to create a VPC peering connection. All data transfered over a connection in the same availablitiy zone is free.

## Flow Logs

- Capture information about IP traffic, traffic going into and out of the network interfaces in your VPC.
- Can publish logs to Cloudwatch or the S3
- Helps diagnose security groups, traffic to the instance or Network Interface

## VPC Endpoint

- Private Connections between VPC and a supported AWS Service, traffic of which would not leave the VPC

1. Interface Endpoint
   1. Elastic Network Interface with private IP from IP address range of your subnet.
   2. Entry point for traffic destined to supported AWS or AWS service endpoint.

2. Gateway Endpoint:
   1. Specify target as route in route table for traffic to supported AWS Service (S3 or DynamoDB)

## Bastion Hsosts

- Instance exposed to public network
- Bastion Host runs on an EC2 instance that is on a public subnet
- Bastion hosts used to ssh into private subnets
- Only part 22 traffic from trusted IPs

## VPN Cloudhub

- Secure communication between sites
  - hub and spoke model with or without a VPC
  - e.g. for multiple offices or internet connections

- Securely connect Multiple VPNs
- VPN connection goes over public subnet

- Requires virtual private gateway with multiple customer gateways
  - Each one needs border gateway protocol and auonomous system number


## Direct Connect

- Create a dedicated private connection between the data center and the VPC
- A dedicated connection is to have an exclusive link, not shared with others.

## Subnets

- Section of a VPC
- Group of Resources
- Groups can have different security or operation needs
- May be public or private

## VPC Network Traffic

- The requested data is sent as a packet which enters the VPC though an internet gateway.
  - A package of data sent over the internet
  - Before entering the subnet, it checks for permissions:
    - who sent the packet
    - who will communicate with the resource in the subnet


## Elastic Network Interface

- Logical Networking component in a VPC that represents a virtual network card.
- Can include: private IPv4 address, 1 Elastic address per private addres, 1 public IPv5 address, 1 or more security groups

## Network Access Control List (ACLs)

- Firewall that controls inbound and outbound traffic
- Control traffic at the subnet level
- All checks and controls packets
- Each subnet must be associated with an ACL
- Stateless Packet filtering
  - They have no memory and will forget once checked
  - Check packets that can go in and out
- Cannot block DNS requests to or from Route 53 Resolver

## Security Groups

- A firewall that controls inbound and outbound traffic.
- Security groups have stateful packet filtering
  - They remember the actions they have taken with packets in the past.

## Dos - Denial of Service Attacks

- Effort to make an application or website inaccessible, DoS causes a flood of data that overloads an application or website network
  - DoS Attck comes from a single source

- Distrobuted Denial of Service DDoS
  - originates from different sources
  - Attacker may use bots - infected computers that flood the app with traffic

## AWS Shield

- Service for Protection against DoS and DDoS attacks
- Shield Standard: protect all aws users at no extra expense
- Shield Advanced: provides attack details and can minimise effects of more complex attacks (paid service)

## AWS WAF

- Web application Firewall
  - monitor application network requests
  - Allow or black network traffic
  - Uses ACL

## AWS GuardDuty

- threat detection service
- Detect threats by monitoring network activity
- Reports threats and fixes recommendations

## Gateway VPC Endpoingt

A gateway vpc endpoint is a fully managed service that allows connectivity from a VPC to AWS services such as S3 without the need for a NAT gateway or public internet gateway. By deploying a Gateway VPC endpoint for S3, the company can ensure all S3 traffic remains within the VPC and does cross the regional boundary. This eliminates regional data transfer charges.

## Systems Manager Sessions Manager

Fully managed service that provies secure and auditable instance management without the need for bastion hosts, VPNs, or SSH keys - it provides secure and auditable access to EC2 instances and eliminates the need for managing and securing SSH keys.

## Systems Manager Patch Manager

Installs security related updates for operating systems on managed nodes - only downloads a small set of patches based on security.

