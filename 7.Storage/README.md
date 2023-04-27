# Storage

## S3 - Simple Storage Service

- Store any type of file
- Set access permissions to a file
- Object level storage
- Unlimited space in storage, but the maximum file size is 5TB
- Object Level Storage
  - each object is made of:
    - data, any type of file
    - metadata, information about what the data is
    - key, unique identifier

## Storage Classes

- S3 Standard: 
  - Ideal for often accessed data
  - High Availablity 
  - Stores data in at least 3 availablity zones
  - Most expensive

- Standard Infrequent Access:
  - Ideal for often accessed data
  - Same level of data availablity as S3 standard
  - Data stored in at least 3 availability zones
  - Lower storage price, but higher price for data retrieval

- S3 One Zone Infrequently Accessed:
  - Similar to above, but data only stored in 1 availablity zone.

- S3 Intelligent Tiering:
  - Requires Automation and Monitoring
  - For data with unknown or frequently changing access
    - Objects moved to S3 Standard-Infrequently-Access class if not accessed for 30 days, and vice versa.

- S3 Glacier:
  - Archiving data
  - Retrieve objects in few minutes
  - Cheaper and Slower

- S3 Glacier Deep Archive:
  - Cheapest
  - For Archives
  - Retrieve Objects in 12 hours

## Cross Origin Resource Sharing (CORS)

- A way for client web applications that are loaded in 1 domain to interact with resources in a different domain
- When client sends a cross origin request, need to enable CORS headers
- Uses XML to enable CORS for a S3 Bucket
- CORS is a browser mechanism
- Build rich client side web apps with S3 and selectively allow CORS to S3 Resources

## S3 Transfer Accelerator

- Manage fast, easy, and secure transfers of files over long geographic, distances between client and S3.
- Use caching for frequently accessed context such as Cloudfront or Elasticache

## S3 Signed URL

- Issue request to provide IAM credentials -> use IAM credentials user keys
- Control access to S3 for limited time

## MACIE

- Security and Compliance enabling service that uses machine learning to identify sensitive data
- Managed service for monitoring data access activities like S3 buckets
- Recognises sensitive data and provides dashboard with Alerts
- Available in US-East-1 and US-East-2

## AWS Data Sync

- Move large amounts of data between on premises and AWS Cloud
- Sync data to
  - Amazon S3
  - Elastic File System
  - FSx for Windows

- Move data from NAS or File System via NFS or SMB
- Move Data 10x Faster
- Schedule Replication
- 
## Athena

- Interactive Query Service to analyse S3 Data using SQL
- Serverless Service
- Pay Per Query
- Read Only
- Integrated with Redshift

## EFS - Elastic File System

- File System
- Data Accessed via file paths
- EFS saves data in multiple availablity zones
- Scaling EFS does not disrupt applications

## Relational Database Service (RDS)

- Service which automates database tasks
- Enables running relational databases in cloud
- Supports:
  - AWS Aurora
  - PostgreSQL
  - MySQL
  - MariaDB
  - Oracle Database
  - SQL Server

- high availablity, and failover support for database instances using Multiple Availablitiy deployments. RDS provisions and maintains a synchronous standby replica in a different availablity zone.
- Read replicas allow you to have a read nly replica by taking a snapshot of the source instance:
  - decreases load by serving read only traffic
  - maintain a copy of databases in a differen region for disaster recovery

- backups may be automated for point in time recovert / database snapshots may be used initiated and done manually

## Aurora

- mySQL, PostgreSQL
- very fast
- distributed, fault tolerant, self healing, serverless
- autohealing, autoscaling, read replicas,
- Continous backup to S3
- Replicates across 3 AZs
- Fully managed

## Redshift

- Big data analytics service
- Gathers information from many sources
- Powered by SQL, AWS hwardware, and machine learning
- Accelerate time to insights with fast, easy, and secure analytics of scale

## Database Migration Service

- Move data between databases, source database and target database
- Source database remains operational during migrational process

Database Migration Service is recommended when:
- Enable testing application against production data
- Enable testing against environment without affecting it
- Combine multiple database into a single database
- Send data to other sources
- Database Migration secure
- Continous data replication, however an EC2 instance is required to perform the replication task

## DocumentDB

- document based database service
- type of NoSQL database
- Supports MongoDB
- Ideal for content management, user profiling, and cataloguing

## Neptune

- Graph Database Service
- Create graphs from your data
- For financial records, supply chain systems, and other centralised digital records

## Quantum ledger Database (QLDB)

- Ledger databaser service
- Provide historical data of all your application changes

## Managed Blockchain

- utilise open source frameworks to create or manage blockchain networks.

## ElastiCache

- Adds caching layers on top of a database
- Stores partof data
- Accelerates application performance
- Improves read times of database requests
- Seen often with Redis and Memcached


## DynamoDB

- Key value and document database
- Extremely quick
- Fully managed multi region, durable
- Built in security, backup and restory and in memory caching for internat scale applications
- DynamoDB stream can be integrated with AWS Lambda
- Security via IAM
- Serverless, scales

## DynamoDB Secondary Index

- Global Secondary Index
  - Index with a partition key, and a sort key that can be different from those on the base table
  - Global secondary index is considered global because queries on index can span all of the data in the base table, across all partitions
  - Global secondary index is stored in its own partition space away from the base table and scales separately from the base table
- Local Secondary Index
  - Index has the same partition key as the base table, but a differernt sort key
  - A local secondary index is local in the sense that every partition of a local index is scoped to a base table partition that has the same parition key value

## DynamoDB Accelerator (DX)

- In memory cache for AWS DynamoDB
- Improve read times for non-relational data
- Improve response time from milli to micro seconds
- Fully managed, flexible, and secure service.
- Secure encryption at rest
- DynamoDB stream is an ordered flow of information about changes to items in a DynamoDB table.
  - Typically used with Lambda
- Implement cross region replication using streams
- Streams only charges you for number of reads

## Snow Family

- Devices that transport data in and out of AWS, up to exabytes of data
- Snowcone: 8TB of data
- Snowball: approximately 80 TB
- Snowmobile: approximately 100 petabytes

## FSx

- Run file systems
  - Windows for Business (Windows encrypts data at rest and in transit)
  - Lustre for high performance
  - Note: POSIX refers to linux
  
## AWS Storage Gateway

- hybrid cloud storage service to connect on premises applications to the cloud
- Gateways include:
  - tape gateway, allows you to backup data to S3 using virtual tape - emulates a physical tape library and allows you to use existing tape based on backup software
  - file gateway, allows you to store and retrieve files in S3 using NFS (Network File system) or SMB (server message block) protocols
  - volume gateway, store and access data on premises and back up to AWS storage such as S3/Glacier/EBS
  