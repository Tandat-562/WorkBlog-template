
---
title: "Week 9 Worklog"
date: 2026-06-21
weight: 1
chapter: false
pre: " <b> 1.9. </b> "

---

## Week 9 Objectives

* Complete Module 06 about AWS database services.
* Review the fundamental concepts of database management systems.
* Distinguish between relational databases, non-relational databases, transactional databases, and analytical data warehouses.
* Understand how to select an appropriate database service for each type of workload.
* Study the architecture and operating mechanisms of Amazon RDS.
* Learn about Amazon Aurora, Aurora Clusters, and the different types of Database Endpoints.
* Distinguish between Multi-AZ Deployments and Read Replicas.
* Study Automated Backups, Manual Snapshots, and Point-in-Time Recovery.
* Study Amazon Redshift and Data Warehouse architecture on AWS.
* Learn about Amazon ElastiCache and the role of caching in improving application performance.
* Distinguish between Valkey, Redis OSS, and Memcached.
* Develop troubleshooting skills related to connectivity, access permissions, routing, Security Groups, and database configuration.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Studied Module 06-01 about database concepts <br> - Distinguished between structured, semi-structured, and unstructured data <br> - Learned about Database Management Systems and common Database types <br> - Analyzed the differences between SQL and NoSQL | 15/06/2026 | 15/06/2026 | https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217 |
| 2 | - Continued studying Module 06-01 <br> - Learned about Primary Keys, Foreign Keys, Indexes, and Relationships <br> - Distinguished between OLTP and OLAP <br> - Analyzed how to select a Purpose-Built Database for each workload | 16/06/2026 | 16/06/2026 | https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217 |
| 3 | - Studied Module 06-02 about Amazon RDS and Amazon Aurora <br> - Learned about the Database Engines supported by Amazon RDS <br> - Analyzed DB Instances, Storage, Subnet Groups, Parameter Groups, and Option Groups <br> - Studied Multi-AZ and Read Replica mechanisms | 17/06/2026 | 17/06/2026 | https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218 |
| 4 | - Practiced creating an Amazon RDS Database <br> - Configured a VPC, DB Subnet Group, and Security Group <br> - Connected EC2 to RDS using a Private Endpoint <br> - Created a Database and Tables and executed basic SQL commands <br> - Checked Automated Backups and Manual Snapshots | 18/06/2026 | 18/06/2026 | https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218 |
| 5 | - Studied Amazon Aurora architecture <br> - Distinguished between Writer Instances and Reader Instances <br> - Learned about Cluster Endpoints, Reader Endpoints, and Instance Endpoints <br> - Analyzed Aurora Replication, Failover, and Read Scaling | 19/06/2026 | 19/06/2026 | https://www.youtube.com/watch?v=qbrobQZrokY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=218 |
| 6 | - Studied Module 06-03 about Amazon Redshift and Amazon ElastiCache <br> - Distinguished between Transactional Databases and Data Warehouses <br> - Learned about Redshift Clusters, Nodes, Columnar Storage, and Massively Parallel Processing <br> - Analyzed the process of loading data from Amazon S3 into Redshift | 20/06/2026 | 20/06/2026 | https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219 |
| 7 | - Studied Amazon ElastiCache <br> - Distinguished between Valkey, Redis OSS, and Memcached <br> - Analyzed Cache-Aside, Write-Through, and Session Caching strategies <br> - Compared RDS, Aurora, Redshift, and ElastiCache <br> - Reviewed and deleted unused practical resources | 21/06/2026 | 21/06/2026 | https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219 |

---

## Week 9 Outcomes

### 1. Completed Module 06

The following main topics were studied:

| Module | Content |
| --- | --- |
| Module 06-01 | Review of Database Concepts |
| Module 06-02 | Amazon RDS and Amazon Aurora |
| Module 06-03 | Amazon Redshift and Amazon ElastiCache |

After completing Module 06, I developed a clearer understanding of how to select database services based on data structure, query types, performance requirements, scalability, and availability.

---

### 2. Database Overview

Databases are used to store, organize, retrieve, and manage data.

A database system commonly includes:

```text
Application
    ↓
Database Connection
    ↓
Database Management System
    ↓
Database
    ↓
Storage
```

The main functions of a Database Management System include:

* Storing data.
* Querying data.
* Updating and deleting data.
* Maintaining data consistency.
* Managing multiple connections.
* Controlling access permissions.
*
    ↓
Storage
```

The main functions of a Database Management System include:

* Storing data.
* Querying data.
* Performing backup and recovery.
* Recording Transactions and Logs.

---

### 3. Data Classification

#### Structured Data

Data is organized according to a defined Schema.

Examples:

* User tables.
* Orders.
* Products.
* Financial transactions.

Structured data is usually suitable for relational databases.

#### Semi-Structured Data

Data has a more flexible structure.

Examples:

* JSON.
* XML.
* Event Logs.
* API Responses.

#### Unstructured Data

Data is not organized into traditional tables.

Examples:

* Images.
* Videos.
* Documents.
* Audio.
* Binary files.

---

### 4. Relational Databases

Relational databases organize data into tables.

Example:

```text
Customers
├── customer_id
├── customer_name
└── email

Orders
├── order_id
├── customer_id
├── order_date
└── total_amount
```

Relationships between tables are created through Keys.

#### Primary Key

* Uniquely identifies a record.
* Must not contain duplicate values.
* Normally cannot be empty.

#### Foreign Key

* References the Primary Key of another table.
* Maintains relationships between tables.
* Helps ensure data integrity.

#### Index

* Improves data retrieval performance.
* May increase write costs and storage usage.
* Should be designed according to actual Query Patterns.

---

### 5. Non-Relational Databases

Non-relational databases are suitable for flexible Schema requirements or large-scale workloads.

Common models:

| Model | Data Examples |
| --- | --- |
| Key–Value | Sessions, Shopping Carts, and User Preferences |
| Document | JSON Documents and Content Catalogs |
| Graph | Social Networks and Recommendation Systems |
| In-Memory | Cache, Leaderboards, and Sessions |
| Time Series | Metrics, IoT Data, and Monitoring Data |

Database selection should be based on Access Patterns rather than only on how data is displayed.

---

### 6. SQL and NoSQL Comparison

| SQL Database | NoSQL Database |
| --- | --- |
| Uses a relatively fixed Schema | Uses a flexible Schema |
| Organizes data into tables | Supports multiple data models |
| Supports JOIN operations | Usually optimized for specific Access Patterns |
| Suitable for complex Transactions | Suitable for large-scale systems |
| Commonly uses SQL | Uses APIs or specialized Query Languages |
| Focuses on data relationships | Focuses on speed and scalability |

No single database type is suitable for every use case. Modern architectures may use multiple database types for different functions.

---

### 7. Transactions and ACID Properties

A Transaction is a group of operations processed as one unit of work.

ACID includes:

#### Atomicity

A Transaction must either complete entirely or make no changes.

#### Consistency

Data must move from one valid state to another valid state.

#### Isolation

Concurrent Transactions must not incorrectly interfere with one another.

#### Durability

After a Transaction is committed, the data must remain permanently stored.

Payment, order management, and financial systems commonly require strong ACID properties.

---

### 8. OLTP and OLAP

#### Online Transaction Processing

OLTP is suitable for:

* Daily transactions.
* Many small write operations.
* Record-level queries.
* Low-latency requirements.
* Current data.

Examples:

* Order processing.
* Payments.
* Account registration.
* Inventory management.

#### Online Analytical Processing

OLAP is suitable for:

* Data analysis.
* Aggregate queries.
* Processing large datasets.
* Reporting and Business Intelligence.
* Historical data.

Examples:

* Revenue reports.
* Customer behavior analysis.
* Trend forecasting.
* Management dashboards.

---

### 9. Purpose-Built Databases

AWS provides multiple database services for different purposes.

Examples:

| Requirement | Suitable Service |
| --- | --- |
| Relational Database | Amazon RDS or Amazon Aurora |
| Key–Value Database | Amazon DynamoDB |
| Data Warehouse | Amazon Redshift |
| In-Memory Cache | Amazon ElastiCache |
| Graph Database | Amazon Neptune |
| Time-Series Database | Amazon Timestream |
| Document Database | Amazon DocumentDB |

The Purpose-Built Database principle helps select an optimized service for each Access Pattern instead of placing all data into a single system.

---

### 10. Amazon RDS Overview

Amazon RDS is a managed relational database service on AWS.

AWS performs many administration tasks:

* Provisioning Database servers.
* Installing Database Engines.
* Managing Storage.
* Performing automated backups.
* Monitoring.
* Replacing failed hardware.
* Applying configured updates.
* Supporting Failover in Multi-AZ deployments.

Users remain responsible for:

* Designing Schemas.
* Creating Tables.
* Writing Queries.
* Managing Database Users.
* Designing Indexes.
* Controlling access.
* Optimizing applications.

---

### 11. Amazon RDS Database Engines

Amazon RDS supports several common Database Engines:

* MySQL.
* PostgreSQL.
* MariaDB.
* Oracle.
* Microsoft SQL Server.
* IBM Db2.
* Amazon Aurora MySQL-Compatible.
* Amazon Aurora PostgreSQL-Compatible.

Engine selection should be based on:

* Application compatibility.
* Database features.
* Licensing model.
* Team experience.
* Performance requirements.
* Scalability.
* Cost.

---

### 12. Amazon RDS Architecture

Main components:

```text
Application
    ↓
RDS Endpoint
    ↓
DB Instance
    ↓
Database Engine
    ↓
Database Storage
```

Within a VPC environment:

```text
Application EC2
      ↓
Security Group
      ↓
RDS Endpoint
      ↓
DB Subnet Group
      ↓
Amazon RDS Database
```

Configuration components:

* DB Instance Class.
* Database Engine.
* Allocated Storage.
* DB Subnet Group.
* Security Group.
* Parameter Group.
* Option Group.
* Backup Retention.
* Maintenance Window.
* Monitoring.

---

### 13. DB Subnet Groups

A DB Subnet Group is a collection of Subnets that Amazon RDS can use.

A Production environment should:

* Use Subnets across multiple Availability Zones.
* Place RDS in Private Subnets.
* Avoid exposing the Database directly to the Internet.
* Allow traffic only from required applications or Bastion Hosts.
* Use Security Group references instead of overly broad CIDR ranges.

Recommended access flow:

```text
Internet
   ↓
Load Balancer
   ↓
Application Server
   ↓
Private RDS Database
```

---

### 14. Multi-AZ Deployment

Multi-AZ is used to improve availability.

Basic model:

```text
Availability Zone A
Primary DB Instance
          ↓
Synchronous Replication
          ↓
Availability Zone B
Standby DB Instance
```

When the Primary fails:

```text
Primary Failure
      ↓
Amazon RDS detects failure
      ↓
Standby becomes Primary
      ↓
Database Endpoint is redirected
```

Characteristics:

* Focuses on High Availability.
* In the traditional Multi-AZ DB Instance model, the Standby is not used directly for Read Traffic.
* Supports automatic Failover.
* The application continues using the same Endpoint.
* Does not completely replace Backup or Disaster Recovery.

---

### 15. Read Replicas

Read Replicas are used to increase read capacity.

Model:

```text
Primary Database
       ↓
Asynchronous Replication
       ↓
Read Replica 1
Read Replica 2
```

Use cases:

* Reporting.
* Dashboards.
* Large read queries.
* Separating Read Workloads from the Primary.
* Supporting certain Disaster Recovery scenarios.

Important considerations:

* Replication is commonly asynchronous.
* Replication Lag may occur.
* The application must connect to the Read Replica Endpoint.
* A Read Replica can be promoted to an independent Database in some situations.

---

### 16. Multi-AZ and Read Replica Comparison

| Multi-AZ | Read Replica |
| --- | --- |
| Improves High Availability | Improves Read Scalability |
| Uses a Standby | Uses a readable Replica |
| Uses synchronous replication in the basic model | Commonly uses asynchronous replication |
| Supports Automatic Failover | Does not automatically replace the Primary using the same mechanism |
| The application uses the main Endpoint | The application connects to a Replica Endpoint |
| Not primarily intended for Read Scaling | Designed for Read Scaling |

Multi-AZ and Read Replicas can be used together in the same architecture to meet Availability and Scalability requirements.

---

### 17. Amazon RDS Backups and Snapshots

#### Automated Backup

* Performed automatically.
* Uses a Backup Retention Period.
* Supports Point-in-Time Recovery.
* Includes the required Snapshot and Transaction Logs.
* Runs within the configured Backup Window.

#### Manual Snapshot

* Created manually.
* Remains until the user deletes it.
* Can be used to create a new Database.
* Suitable before performing significant changes.

Recovery process:

```text
RDS Backup or Snapshot
          ↓
Restore
          ↓
New DB Instance
          ↓
New Endpoint
          ↓
Validate Data
          ↓
Update Application Connection
```

A Restore operation does not normally overwrite the current DB Instance. It usually creates a new DB Instance.

---

### 18. Point-in-Time Recovery

Point-in-Time Recovery allows a Database to be restored to a specific point within the Backup Retention Period.

Example:

```text
10:00 – Database operates normally
10:15 – Data is accidentally deleted
10:20 – The issue is discovered
```

The Database can be restored to a time before 10:15 when the required Backup and Transaction Logs are available.

After restoring, the following must be checked:

* Data.
* Users and permissions.
* Parameters.
* Security Groups.
* Application Endpoint configuration.
* Data integrity.

---

### 19. Amazon Aurora

Amazon Aurora is a relational database compatible with MySQL and PostgreSQL.

Aurora separates the Compute and Storage layers:

```text
Aurora DB Cluster
├── Writer Instance
├── Reader Instance 1
├── Reader Instance 2
└── Distributed Cluster Storage
```

Characteristics:

* Storage is managed at the Cluster level.
* One Writer Instance handles write operations.
* Multiple Reader Instances can be used.
* Supports Failover between Instances.
* Supports Read Scaling.
* Integrates with Backup, Monitoring, and AWS KMS.

---

### 20. Aurora Endpoints

#### Cluster Endpoint

* Normally connects to the Writer Instance.
* Used by applications for write operations.
* Automatically points to the new Writer after Failover.

#### Reader Endpoint

* Distributes read connections across Reader Instances.
* Used to scale Read Workloads.
* Is not a Load Balancer at the individual SQL statement level.

#### Instance Endpoint

* Points to a specific DB Instance.
* Commonly used for administration or testing.
* Does not automatically distribute connections to other Instances.

Application flow:

```text
Write Request
     ↓
Cluster Endpoint
     ↓
Writer Instance

Read Request
     ↓
Reader Endpoint
     ↓
Reader Instances
```

---

### 21. Amazon Redshift

Amazon Redshift is a managed Data Warehouse service on AWS.

Redshift is suitable for:

* Business Intelligence.
* Reporting.
* Historical data analysis.
* Aggregate queries.
* Large-scale data analysis.
* Dashboard development.
* Analysis of data from multiple sources.

Redshift is not designed to directly replace an OLTP database for individual application transactions.

---

### 22. Amazon Redshift Architecture

Redshift Cluster model:

```text
Client Application
        ↓
Leader Node
        ↓
Compute Nodes
        ↓
Node Slices
        ↓
Columnar Data Storage
```

#### Leader Node

* Receives Client connections.
* Analyzes Queries.
* Creates Execution Plans.
* Distributes work to Compute Nodes.
* Aggregates results.

#### Compute Node

* Stores and processes data.
* Performs most computational work.
* Can be divided into Slices.

---

### 23. Columnar Storage

In Row-Based Storage, the data belonging to one row is stored together:

```text
Customer 1: ID, Name, City, Revenue
Customer 2: ID, Name, City, Revenue
```

In Columnar Storage, data belonging to one column is stored together:

```text
ID:      1, 2, 3, 4
Name:    A, B, C, D
City:    HN, HCM, DN, HP
Revenue: 100, 200, 300, 400
```

Columnar Storage is suitable for analytics because it:

* Reads only the required columns.
* Supports efficient compression.
* Improves aggregate query performance.
* Reduces the amount of scanned data.

---

### 24. Massively Parallel Processing

Amazon Redshift divides query workloads across multiple Compute Resources for parallel processing.

Processing flow:

```text
SQL Query
    ↓
Leader Node creates execution plan
    ↓
Query is divided into smaller tasks
    ↓
Compute Nodes process tasks in parallel
    ↓
Results are combined
    ↓
Return result to client
```

Performance depends on:

* Data distribution.
* Sort Keys.
* Distribution Style.
* Cluster or Workgroup size.
* SQL query quality.
* Amount of data scanned.
* Workload Management.

---

### 25. Loading Data into Amazon Redshift

A common flow:

```text
Operational Systems
        ↓
Extract Data
        ↓
Amazon S3
        ↓
COPY Command
        ↓
Amazon Redshift
        ↓
Business Intelligence Tool
```

When loading data from Amazon S3, the following should be checked:

* Redshift IAM Role.
* S3 read permissions.
* Bucket and Object Key.
* Region.
* File Format.
* Data Type.
* Delimiter.
* Compression.
* Error Logs.

---

### 26. Amazon ElastiCache

Amazon ElastiCache provides a managed In-Memory Data Store or Cache.

Flow without Cache:

```text
Application
     ↓
Database
     ↓
Return Data
```

Flow with Cache:

```text
Application
     ↓
Check ElastiCache
  ┌───────┴────────┐
Cache Hit       Cache Miss
   ↓                ↓
Return Data       Query Database
                    ↓
                Update Cache
                    ↓
                Return Data
```

Benefits:

* Reduces latency.
* Reduces the number of Database Queries.
* Increases Request processing capacity.
* Improves user experience.
* Reduces load on Backend systems.

---

### 27. Valkey, Redis OSS, and Memcached

| Valkey or Redis OSS | Memcached |
| --- | --- |
| Supports multiple data structures | Uses a simple Key–Value model |
| Supports Replication | Does not support Replication using the same mechanism |
| Can support Backups | Usually does not focus on Backups |
| Supports Pub/Sub | Does not provide the same complete feature set |
| Suitable for Sessions and Leaderboards | Suitable for simple Caching |
| Supports Primary and Replica Nodes | Can distribute data across multiple Nodes |
| Can support Automatic Failover | Uses a simpler design |

The selection depends on:

* Data type.
* Persistence requirements.
* High Availability.
* Data structures.
* Scalability.
* Operational complexity.

---

### 28. Caching Strategies

#### Cache-Aside

```text
Application checks the Cache
        ↓
Cache Miss
        ↓
Read from Database
        ↓
Write Data to Cache
        ↓
Return Result
```

Advantages:

* Only accessed data is cached.
* Easy to apply.
* The application controls the caching process.

Disadvantages:

* The first Request must still read from the Database.
* Stale data may appear.

#### Write-Through

```text
Application writes data
        ↓
Cache is updated
        ↓
Database is updated
```

Advantages:

* Cache usually contains current data.
* Reduces Cache Misses after writes.

Disadvantages:

* Increases write latency.
* May cache data that is rarely read.

#### Time to Live

TTL determines how long a Cache Entry is retained.

The following factors must be balanced:

* Data freshness.
* Cache Hit rate.
* Database load.
* Memory capacity.

---

### 29. Database Security

Security layers that should be checked:

```text
IAM Permission
      ↓
VPC and Subnet
      ↓
Route Table
      ↓
Security Group
      ↓
Database Authentication
      ↓
Encryption
      ↓
Database User Permission
```

Security principles:

* Place the Database in Private Subnets.
* Do not open Database ports to `0.0.0.0/0`.
* Allow traffic only from the application's Security Group.
* Encrypt data at rest.
* Use TLS for data in transit.
* Protect Secrets and Passwords.
* Apply Least Privilege to Database Users.
* Monitor Logs and Audits.
* Perform regular backups.
* Regularly test the Restore process.

---

### 30. Database Monitoring

Metrics that should be monitored:

#### Amazon RDS and Aurora

* CPUUtilization.
* DatabaseConnections.
* FreeStorageSpace.
* FreeableMemory.
* ReadIOPS.
* WriteIOPS.
* ReadLatency.
* WriteLatency.
* ReplicaLag.
* Deadlock.
* Query Throughput.

#### Amazon Redshift

* CPUUtilization.
* DatabaseConnections.
* QueryDuration.
* ReadIOPS.
* WriteIOPS.
* PercentageDiskSpaceUsed.
* QueryQueueLength.

#### Amazon ElastiCache

* CPUUtilization.
* EngineCPUUtilization.
* CurrConnections.
* CacheHits.
* CacheMisses.
* Evictions.
* FreeableMemory.
* ReplicationLag.

Monitoring helps detect problems before the system is significantly affected.

---

## Practical Issues Resolved

### 1. Unable to Connect to Amazon RDS

The following items were checked:

* The DB Instance was in the `Available` state.
* Endpoint and Port.
* VPC.
* DB Subnet Group.
* Route Table.
* Security Group.
* Network ACL.
* Public Accessibility.
* Username and Password.
* Database Name.
* DNS Resolution.
* Database Service.

Commands that can be used to test connectivity:

```bash
nc -zv <rds-endpoint> 3306
```

Or:

```bash
mysql -h <rds-endpoint> -u <username> -p
```

---

### 2. RDS Connection Timeout

The causes were commonly related to networking:

* The Security Group did not allow the Database Port.
* The Source IP or Security Group was incorrect.
* RDS was located in a Private Subnet.
* The Client did not have a Route to RDS.
* A Network ACL blocked the traffic.
* The Endpoint or Port was incorrect.
* DNS Resolution failed.

Distinction:

* `Connection timeout` is normally related to networking.
* `Access denied` is normally related to Username, Password, or Database Permissions.

---

### 3. Unable to Sign In to the Database

The following possible causes were checked:

* Incorrect Master Username.
* Incorrect Password.
* Connected to the wrong Database.
* The User had not been granted permissions.
* The Host was not permitted to connect.
* The Password contained characters processed specially by the Shell.
* The Authentication Plugin was incompatible.

---

### 4. Confusion Between Multi-AZ and Read Replicas

Resolution:

* Determine whether the objective is High Availability or Read Scaling.
* Do not send Read Queries to the traditional Multi-AZ Standby.
* Use the Read Replica Endpoint for Read Workloads.
* Monitor Replication Lag when using Read Replicas.
* Do not treat a Read Replica as a complete replacement for Backup.

---

### 5. Application Could Not Connect After Restoring a Snapshot

Possible causes:

* The Restore operation created a new DB Instance.
* The Endpoint changed.
* The correct Security Group was not attached.
* The Parameter Group differed from the original Database.
* The DB Subnet Group was not appropriate.
* Username or permissions were different.
* The application still used the old Endpoint.

---

### 6. Aurora Reader Endpoint Could Not Process Write Operations

Cause:

* The Reader Endpoint is designed for Read Connections.
* The application sent write statements to the Reader.
* The Connection Pool did not separate Read and Write connections.

Resolution:

* Use the Cluster Endpoint for write operations.
* Use the Reader Endpoint for read operations.
* Separate the application's connection configurations.

---

### 7. Amazon Redshift Could Not Load Data from Amazon S3

The following items were checked:

* The IAM Role was attached to Redshift.
* The Role had `s3:GetObject` permission.
* Bucket and Object Key.
* Region.
* `COPY` command syntax.
* File Format.
* Delimiter.
* Data Type.
* Encoding.
* Error Tables and Load Errors.

---

### 8. Amazon Redshift Query Performance Was Slow

The following possible causes were analyzed:

* Too much data was scanned.
* Appropriate Filters were not used.
* Distribution Style was not optimized.
* Sort Keys were unsuitable.
* Data Skew.
* Query Queue.
* Workload Management.
* Insufficient Cluster or Serverless Capacity.
* Queries joined large datasets.

---

### 9. Unable to Connect to Amazon ElastiCache

The following possible causes were checked:

* ElastiCache provides only a Private Endpoint.
* The Client was not located in the VPC and had no connection to the VPC.
* The Security Group did not allow the required Port.
* Incorrect Endpoint.
* Incorrect Port.
* TLS Configuration.
* Subnet Group.
* Route Table.
* Network ACL.
* The Cluster was being created or maintained.

---

### 10. Low Cache Hit Rate

Possible causes:

* TTL was too short.
* Cache Keys were inconsistent.
* Data was rarely accessed again.
* Cache Eviction occurred.
* Memory capacity was insufficient.
* The application did not use Cache at the correct point.
* Cache entries were frequently deleted.

Improvements:

* Standardize Cache Keys.
* Adjust the TTL.
* Monitor Cache Hits and Cache Misses.
* Increase Capacity when required.
* Cache only appropriate data.
* Review the Invalidation strategy.

---

## Database Troubleshooting Process Developed

When an application cannot access a Database, the following order should be used:

1. Identify the Database type and Endpoint.
2. Check the resource status.
3. Check the Endpoint and Port.
4. Check the VPC, Subnet, and Route Table.
5. Check the Security Group and Network ACL.
6. Check DNS Resolution.
7. Check the Username, Password, and Authentication mechanism.
8. Check Database User permissions.
9. Check the Connection Limit.
10. Check Database Logs and CloudWatch Metrics.
11. Check Queries and application Logs.
12. Check Backups or Replicas when the issue is related to data.

This process helps distinguish between networking, Authentication, Authorization, Capacity, and Query Performance issues.

---

## Skills Developed

* Distinguishing between relational and non-relational databases.
* Understanding Primary Keys, Foreign Keys, and Indexes.
* Distinguishing between OLTP and OLAP.
* Understanding the Purpose-Built Database principle.
* Understanding Amazon RDS architecture.
* Configuring DB Subnet Groups and Security Groups.
* Distinguishing between Multi-AZ and Read Replicas.
* Understanding Automated Backups, Snapshots, and Point-in-Time Recovery.
* Understanding Amazon Aurora architecture.
* Distinguishing between Cluster, Reader, and Instance Endpoints.
* Understanding Amazon Redshift architecture.
* Understanding Columnar Storage and Massively Parallel Processing.
* Understanding the role of Amazon ElastiCache.
* Distinguishing between Valkey, Redis OSS, and Memcached.
* Analyzing Caching strategies.
* Troubleshooting Database connectivity and performance.

---

## Self-Evaluation

* Completed all content in Module 06.
* Understood the fundamental concepts of Database Management Systems.
* Able to distinguish between Transactional Databases, Analytical Databases, and Caches.
* Understood the role of Amazon RDS in reducing Database administration work.
* Able to distinguish between Multi-AZ Deployments and Read Replicas.
* Understood Amazon RDS backup and recovery mechanisms.
* Understood Amazon Aurora Cluster architecture.
* Understood the use cases of Amazon Redshift.
* Understood how ElastiCache reduces Database load.
* Improved troubleshooting skills based on networking, Authentication, permissions, and performance.

Areas for further improvement:

* Practice additional SQL commands.
* Study Database Normalization in greater depth.
* Practice Failover with Amazon RDS Multi-AZ.
* Monitor Read Replica Replication Lag.
* Practice Aurora Reader Auto Scaling.
* Study Amazon RDS Proxy.
* Practice Amazon Redshift Serverless.
* Optimize Distribution Keys and Sort Keys.
* Practice ElastiCache with a real application.
* Study DynamoDB and other NoSQL databases in greater depth.
* Optimize Database and Storage costs.

---

## Next Steps

* Join group discussions to select an AWS project topic.
* Analyze business requirements and the problem to be solved.
* Identify the system's target users.
* Build a list of Functional Requirements and Non-Functional Requirements.
* Research AWS services that can be applied to the project.
* Design the initial AWS architecture diagram.
* Divide responsibilities among team members.
* Identify the components that need to be developed:

  * Frontend.
  * Backend API.
  * Database.
  * File Storage.
  * AI Service.
  * Monitoring.
  * Security.
  * Notification.
  * Report Generation.

* Prepare to move into the Capstone project design and implementation phase.

---

