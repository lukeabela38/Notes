# EC2 - Elastic Cloud Compute

## What is EC2?

A virtual server running in the cloud
1. Scaling of capacity up and down
2. Access resources on demand, with no upfront investment, and only pay for what you need.

## EC2 Types

1. General Purpose: Balance Computing, Memory, and Network Resources. Great for Application and Gaming Servers, backends, small and medium sized backends.
2. Compute Optimised: When there is a need for high compute, generally considered best for application servers, gaming, and web applications.
3. Memory Optimised: Deliver large dataset workloads quickly. Memory is a temporary storage area. Loads and holds data, and processes before a computer can run on it. Ideal when there are large amounds of data that need to be preloaded before running the app.
4. Accelerated Computing: Hardward accelerators, used to boost data processing. Graphics Applications and streaming.
5. Storage Optimised: for large datasets on local storage, large filesystems, data warehouses, online transaction systems.

## EC2 States

1. Pending: Preparing to run -> not billed
2. Running: billed
3. Stopping: only billed if preparing to hibernate
4. Hibernating - save contents from RAM to EBS root volume, allowing instance and attached root volumes to persist. It retains the private IPv4 Address.

## AMIs - Amazon Machine Image

1. It is a template which contains software configurations.
2. This is info which is required at launch time of the EC2 instance.
3. Public AMIs may be found in the Amazon Marketplace

## Advantages of AMIs

1. Preinstall any required packages
2. No malware threats
3. Faster boot times
4. No Hourly Charges
5. Maintainable over time
6. Stored in S3
7. Specific to account and region

## Placement Groups

Placement groups are logical groups of instances

1. Cluster - Instances closer together in an availablity zone, sharing one rack. Same availablitiy zone, in the same region. Instances span peered VPCs, making it great for low latency applications.
2. Partition - Spread instances such that they do not share underlying hardware, reducing the risk of correlated hardware failures for your application. A group of instances in a logical segmentation is known as a partition. Each partition has its own set of racks, with each rack having its own network and power source.
3. Spread - strictly places a small group of instances acoss a distinct underlying hardware to reduce correlated failure. Each group of instances is placed on distinct racks, each with its own network and power source. This is ideal for applications with a small number of critical instances which are to be kept separate. This configuration can span multiple availablity Zones.

## EC2 Pricing

1. On Demand Instances: for short term workloads with no upfront cost. Pay for what you use.
2. Savings Plan: Plan for usage over a 1/3 year term. Instances would be available for a discounted price. If the budget is surpassed, the instances rever to normal prices.
3. Spot Instances: reqyesr spare EC2 capacity for up to 90% off demand price.
4. Dedicated Hosts: physical EC2 server dedicated for your exclusive use. Can help reduce costs by allowing you to use your server bound software licenses.
5. Reserved Instances:
   1. Standard RIs: These provide the most significant discount (up to 72% off On-Demand) and are best suited for steady-state usage.
   2. Convertible RIs: These provide a discount (up to 54% off On-Demand) and the capability to change the attributes of the RI as long as the exchange results in the creation of Reserved Instances of equal or greater value. Like Standard RIs, Convertible RIs are best suited for steady-state usage.
   3. Scheduled RIs: These are available to launch within the time windows you reserve. This option allows you to match your capacity reservation to a predictable recurring schedule that only requires a fraction of a day, a week, or a month.

## EC2 Scaling

Only use the resources you need whilst having the flexibility to grow. Requires an architecture capable of changing on demand.

## Autoscaling

Servers may get more requests than they can handle, with too many requests causing timeouts, and outages. Autoscaling lets you add or remove EC2 instances automatically. It automates the capacity meet demands.

Approaches Include:
1. Dynamic Scaling: respond directly to changing demand
2. Predictive Scaling: Schedule Number of instances based on predicted demand.
3. Combined Dynamic and Predictive Scaling

Autoscaling can be considered as a buffer on top of instamces:
1. Setup a minimum capacity, and a maximum capacity, and the desired number
2. Can work in Multiple Availablity Zones

## Auto Scaling Alarms

1. Monitor metrics such as CPU usage, and network in/network out
2. Scale based on Cloudwatch Alarms

## Benefits of Autoscaling Groups

1. Better fault tolerance
2. Better availablity and cost management
3. Only pay for the underlying architecture
4. Scaling can be based on manual, schedule, on demand, target tracking, or step scaling.
5. Cooldown Period - don't launch or terminate before previous scaling has occurred - note: cooldowns are ignored if health checks failed. You can reduce cost by having a shorter time of 180 seconds when scaling in.

## Autoscaling Group Default Termination Policy

1. Find availablity zone with most instances
2. If many instances, choose one with oldest launch configuration

## AutoScaling Termination Hooks

1. Extra steps before EC2 is launched or terminated

## Elastic Load Balancing

1. Service distributes application traffic across services
2. Load Balancing serves as single point of contact for incoming web traffic
   1. i.e. traffic hits load balancer first, then it spread out between resources
   2. Ensures no resource gets overloaded
3. Elastic Load balancer scales automatically
4. Can work across Multipe Availablity Zones
5. Enforces Stickiness with Cookies
6. Secure tunell via HTTPS

## TroubleShooting

1. 4XX -> Client Side Errors
2. 5XX -> Application Errors
3. 503 -> Capacity or No Registered Targets
4. ELB logs all access requests -> view from cloudwatch

## Health Checks

1. Load Balancer sends request to each target checking status
2. Passive Health Checks: detect atrget is unhealthy before it is unreported as such
3. Health checks are done on port and route

## Application Load Balancer

1. Operates at Layer 7, http/https

## Network Load Balancer

1. Operates at Layer 4, routes traffic with AWS VPC


## Gateway Load Balancer

Fully managed, network layer load balancer that routes traffic to targets in VPCs and on-premises networks. It is designed to handle millions of requests per second while maintaining high performance and low latencies. It also integrates with Amazon VPC to allow traffic to flow between your on-premises data centers and VPCs.

## Load Balancer Stickiness

Stickiness: same client is redirected to same instance
1. For Classical Load Balancer, Application Load Balancer

Stickiness implemented using cookies:
1. Users don't lose their session data
2. Slight Load Imbalance

## ELB Cross Zone Load Balancing

1. Load Balancer node distributes across registered targets in all enabled AZs when cross zone load balancing enabled.
2. Reduces unvene distribution of traffic when clinets have an unequal number of instances in each availablity zone.
3. Free in Application Load Balancing.

## SSL Certs

1. Secure Socket Layer (SSL) -> encrypt connections
2. Transport Layer Security (TLS) 

Certificates have expiration date.
SSL protocols use several SSL ciphers to encrypt data over the internet.

Manage your own certificates using AWS certificate manager.

## ELB Server Name Indication (SNI)

Server name indication allows servers to host multiple TLS certs for multiple sites underneath a single IP

With SNI, the client indicates which hostname it is attempting to connect at the start of the handshaking process.

- Applies to Application Load Balancing, and Network Load Balancing.
- It is also supported by Cloudfront.

## Connection Draining

Load Balancer will allow existing requests to an instance to complete, but no new requests. 

Minimum time -> 1 seconds
Maximum time -> 3600 seconds
Default -> 300 seconds

The maximum timeout is not applicable to unhealth instances.

## Instance Stores

- Storage volume which acts as a physical hard drive
- Temporary storage for the EC2 instance
- Data in the instance store persists during the lifetime of the instance. 
  - If the instance reboots, data will persist.
- When instance hibernates or terminates, any data in the instance store will be lost.
- If instance starts from a stopped state, it might be on another host where the used instance store does not exist.
- Typically recommended for temp files.

## Elastic Block Store

- A service which provides storage volumes, typically used for data which must persist.
- It is good pracice to backup data with AWS EBS snapshots
- After creating an EBS volume, you can attach it to an AWS EC2 instance. If the EC2 instance is stopped or termnated, all data on the EBS volume remains

## EBS Snapshots

EBS snapshot is an incremental data backup:
- First backup of volume backs up all data
- Seubsequent backups copy only a block of data that has changed since the last snapshot
- Saves on storage cosst by not duplicating data
- Only data unique to snapshot is removed when deleting the snapshot, if EC2 instance stops or is terminated, all data on EBS volume remains.

## AppFLow

Appflow is a fully managed integration service allowing to securely exchange data between software as a service applications and AWS S3 and Redshift. Appflow helps to remove ec2 as the middle layer which slows down the process of data transmissions and introduces an additional variable. Appflow is a fully managed AWS Service, thus reducing the operational overhead.