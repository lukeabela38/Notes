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
