
---
title: "Week 6 Worklog"
date: 2026-05-30
weight: 1
chapter: false
pre: " <b> 1.6. </b> "

---

## Week 6 Objectives

* Begin studying Module 04 about AWS Storage services.
* Understand the differences between Object Storage, Block Storage, and File Storage.
* Study the architecture and operating mechanisms of Amazon S3.
* Understand the structure of Buckets, Objects, Object Keys, and Prefixes in Amazon S3.
* Learn about S3 Storage Classes and how to select an appropriate storage class based on access requirements.
* Study S3 Versioning, Lifecycle Rules, and Access Points.
* Practice deploying a Static Website using Amazon S3.
* Integrate Amazon CloudFront for content distribution.
* Build a centralized backup plan using AWS Backup.
* Improve troubleshooting skills related to access permissions, Versioning, Lifecycle, and Backup.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Studied Module 04-01 <br> - Learned about the main storage models on AWS <br> - Distinguished between Object Storage, Block Storage, and File Storage <br> - Identified use cases for S3, EBS, and EFS | 25/05/2026 | 25/05/2026 | https://www.youtube.com/watch?v=hsCfP0IxoaM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=103 |
| 2 | - Studied Module 04-02 <br> - Learned about Amazon S3, S3 Access Points, and Storage Classes <br> - Analyzed how to select a storage class based on access frequency and cost | 26/05/2026 | 26/05/2026 | https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104 |
| 3 | - Practiced Lab 000057 <br> - Created an S3 Bucket and uploaded Objects <br> - Configured Static Website Hosting <br> - Tested the Website Endpoint | 27/05/2026 | 27/05/2026 | https://000057.awsstudygroup.com/vi/ |
| 4 | - Configured S3 Versioning <br> - Tested updating and deleting Objects <br> - Restored previous versions <br> - Studied Delete Markers and Version IDs | 28/05/2026 | 28/05/2026 | https://000057.awsstudygroup.com/vi/ |
| 5 | - Studied S3 Lifecycle Management <br> - Created Lifecycle Rules for Objects <br> - Analyzed data transitions between Storage Classes <br> - Studied Expiration and Noncurrent Version Expiration | 29/05/2026 | 29/05/2026 | https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104 |
| 6 | - Practiced AWS Backup <br> - Created a Backup Vault and Backup Plan <br> - Configured Backup Rules and Resource Assignments <br> - Monitored Backup Job status | 30/05/2026 | 30/05/2026 | https://000013.awsstudygroup.com/vi/ |
| 7 | - Configured a CloudFront Distribution for S3 content <br> - Reviewed Module 04-01 and Module 04-02 <br> - Checked Bucket access permissions <br> - Reviewed and deleted unused resources | 31/05/2026 | 31/05/2026 | https://000057.awsstudygroup.com/vi/ |

---

## Week 6 Outcomes

### 1. Completed the First Part of Module 04

The following topics were studied:

| Content | Main Knowledge |
| --- | --- |
| Module 04-01 | Overview of AWS storage models and storage services |
| Module 04-02 | Amazon S3, S3 Access Points, and S3 Storage Classes |
| Practical Exercises | S3 Static Website, Versioning, Lifecycle, CloudFront, and AWS Backup |

After this week, I understood how to select a storage service based on data type, access method, durability, performance, and cost.

---

### 2. Distinguishing Between Storage Models

#### Object Storage

Data is stored as Objects, and each Object includes:

* Data.
* Metadata.
* Object Key.
* Version ID when Versioning is enabled.

Amazon S3 is an Object Storage service suitable for:

* Images and videos.
* Static Websites.
* Backups.
* Logs.
* Data Lakes.
* Application files.
* Content distributed through CloudFront.

#### Block Storage

Data is organized into Blocks and is normally attached directly to a server.

Amazon EBS is suitable for:

* EC2 Root Volumes.
* Databases.
* File Systems.
* Applications requiring low latency.

#### File Storage

Data is accessed using a directory-and-file structure.

Amazon EFS or Amazon FSx is suitable for:

* Shared File Systems.
* Multiple servers requiring access to the same data.
* Applications using NFS or SMB.

---

### 3. Amazon S3 Architecture

Basic structure:

```text
AWS Account
    ↓
S3 Bucket
    ↓
Prefix or Folder
    ↓
Object
```

Each Object is identified by:

* Bucket Name.
* Object Key.
* Version ID when Versioning is enabled.

Example:

```text
Bucket: fcj-storage-lab
Object Key: images/architecture/aws-diagram.png
```

Understood that folders displayed in the S3 interface are simulated using Prefixes in Object Keys.

---

### 4. Amazon S3 Characteristics

Amazon S3 provides:

* Flexible storage scalability.
* Highly durable Object Storage.
* Data access through API, Console, CLI, or SDK.
* Permission management using IAM Policies and Bucket Policies.
* Versioning support.
* Lifecycle support.
* Integration with CloudFront.
* Data encryption support.
* Events when Objects are created, updated, or deleted.

Main use cases:

* Static Websites.
* Backup and Archive.
* Data Lakes.
* Document storage.
* Content distribution.
* Log storage.
* Application file uploads.

---

### 5. S3 Storage Classes

| Storage Class | Use Case |
| --- | --- |
| S3 Standard | Frequently accessed data |
| S3 Intelligent-Tiering | Data with unpredictable access patterns |
| S3 Standard-IA | Infrequently accessed data that requires rapid retrieval |
| S3 One Zone-IA | Infrequently accessed data that can be recreated |
| S3 Glacier Instant Retrieval | Long-term data requiring immediate retrieval |
| S3 Glacier Flexible Retrieval | Long-term data where a longer restoration period is acceptable |
| S3 Glacier Deep Archive | Data stored for a very long time and accessed very rarely |

Storage Class selection should be based on:

* Access frequency.
* Data retention period.
* Retrieval requirements.
* Ability to recreate the data.
* Data importance.
* Storage and retrieval costs.

---

### 6. S3 Intelligent-Tiering

S3 Intelligent-Tiering is suitable when the frequency of data access cannot be predicted accurately.

The service automatically monitors access patterns and moves Objects between appropriate access tiers.

Benefits:

* Reduces manual management.
* Reduces the risk of selecting the wrong Storage Class.
* Suitable for data with changing access frequency.
* Can optimize costs without requiring application changes.

---

### 7. S3 Access Points

An S3 Access Point provides a dedicated Endpoint for accessing a Bucket.

Example:

```text
S3 Bucket
├── Access Point for Application A
├── Access Point for Application B
└── Access Point for the Analytics Team
```

Each Access Point can have:

* A unique name.
* An Access Point Policy.
* Public Access settings.
* A Network Origin.
* Separate access permissions for each application.

Benefits:

* Simplifies Bucket Policies.
* Separates permissions by application or team.
* Supports managing Buckets used by multiple consumers.
* Can restrict access to a specific VPC.

---

### 8. S3 Versioning

Versioning stores multiple versions of the same Object.

Example:

```text
report.pdf
├── Version 1
├── Version 2
└── Version 3
```

Benefits:

* Restores data after accidental overwrites.
* Restores data after accidental deletion.
* Tracks change history.
* Helps protect data from user or application errors.

When an Object is deleted from a Versioning-enabled Bucket, Amazon S3 normally creates a Delete Marker instead of immediately deleting all versions.

An Object can be restored by:

* Deleting the Delete Marker.
* Downloading a previous version.
* Copying an earlier version to create the current version.

---

### 9. S3 Lifecycle Management

Lifecycle Rules automatically manage data based on the age of an Object.

Example:

```text
Day 0: S3 Standard
   ↓
Day 30: S3 Standard-IA
   ↓
Day 90: S3 Glacier Flexible Retrieval
   ↓
Day 365: Delete Object
```

Lifecycle Rules can apply to:

* Current Versions.
* Noncurrent Versions.
* Objects with a specific Prefix.
* Objects with specific Tags.
* Incomplete Multipart Uploads.

Benefits:

* Optimizes costs.
* Reduces manual operations.
* Automatically processes old data.
* Supports organizational data retention policies.

---

### 10. Static Website Hosting with Amazon S3

Completed the following tasks:

* Created a Bucket.
* Uploaded HTML, CSS, and image files.
* Enabled Static Website Hosting.
* Configured the Index Document.
* Configured the Error Document.
* Tested the Website Endpoint.
* Adjusted access permissions.

Access flow:

```text
User
    ↓
S3 Website Endpoint
    ↓
index.html
    ↓
CSS, JavaScript, and Images
```

S3 Static Website Hosting is suitable for:

* Portfolios.
* Landing Pages.
* Project documentation.
* Introduction websites.
* Frontends that do not require Server-Side Processing.

---

### 11. Integrating Amazon CloudFront

CloudFront was used to distribute S3 content to users through Edge Locations.

Processing flow:

```text
User
    ↓
CloudFront Edge Location
    ↓
CloudFront Cache
    ↓
Amazon S3 Origin
```

Benefits:

* Reduces latency.
* Caches content closer to users.
* Reduces the number of Requests sent directly to S3.
* Supports HTTPS.
* Allows the S3 Bucket to remain private.
* Supports access control for the Origin.

---

### 12. AWS Backup Overview

AWS Backup provides centralized backup management.

Main components:

```text
Backup Plan
    ↓
Backup Rule
    ↓
Resource Assignment
    ↓
Backup Job
    ↓
Recovery Point
    ↓
Backup Vault
```

Completed the following tasks:

* Created a Backup Vault.
* Created a Backup Plan.
* Configured a Backup schedule.
* Selected resources.
* Monitored Backup Jobs.
* Checked Recovery Points.
* Studied Restore Jobs.

Benefits:

* Centralized Backup management.
* Automated backup schedules.
* Retention Period configuration.
* Backup status monitoring.
* Support for multiple AWS services.

---

## Practical Issues Resolved

### 1. Unable to Access the S3 Static Website

The following elements were checked:

* Static Website Hosting was enabled.
* The Index Document used the correct filename.
* The Object had been uploaded.
* Bucket Policy.
* Block Public Access.
* Website Endpoint URL.
* Correct uppercase and lowercase characters in the Object Key.

---

### 2. Object Access Denied

The following possible causes were checked:

* The IAM Policy did not allow access.
* The Bucket Policy did not allow access.
* An Explicit Deny was applied.
* Block Public Access was enabled.
* Object Ownership settings.
* KMS Key Policy.
* Incorrect Bucket or Object Key.

---

### 3. Versioning Could Not Restore Data

The following elements were checked:

* Whether Versioning had been enabled before the Object was updated.
* Version ID.
* Delete Marker.
* `s3:GetObjectVersion` permission.
* `s3:ListBucketVersions` permission.

---

### 4. Lifecycle Rule Did Not Work as Expected

The following possible causes were reviewed:

* Incorrect Prefix or Tag Filter.
* The Object was not old enough.
* The Rule was not enabled.
* Minimum Storage Duration requirements.
* Current Versions and Noncurrent Versions were configured differently.
* The transition process did not occur immediately.

---

### 5. Backup Job Failed

The following components were checked:

* AWS Backup IAM Role.
* Resource Assignment.
* Backup Vault.
* Backup Window.
* Service permissions.
* Resource status.
* CloudWatch Events and SNS Notifications.

---

## Skills Developed

* Distinguishing between Object, Block, and File Storage.
* Designing Bucket and Object Key structures.
* Selecting appropriate S3 Storage Classes.
* Creating and managing S3 Access Points.
* Configuring S3 Versioning.
* Building Lifecycle Rules.
* Deploying a Static Website on S3.
* Integrating CloudFront with S3.
* Creating Backup Vaults and Backup Plans.
* Troubleshooting access and data management issues on Amazon S3.

---

## Self-Evaluation

* Developed a stronger understanding of Amazon S3 architecture.
* Able to select an appropriate Storage Class based on requirements.
* Learned how to use Versioning to protect Objects.
* Able to configure Lifecycle Rules for cost optimization.
* Able to deploy a Static Website using Amazon S3.
* Understood the role of CloudFront in content distribution.
* Able to build a basic Backup Plan.
* Improved skills in checking IAM Policies, Bucket Policies, and Backup status.

Areas for further improvement:

* Study S3 Encryption in greater depth.
* Practice using S3 Access Points through a VPC.
* Study S3 Object Lock.
* Practice Cross-Region Replication.
* Design Lifecycle Rules for data with multiple versions.
* Test Restore Jobs using AWS Backup.

---

## Next Steps

* Continue Module 04 with:

  * S3 Static Website and CORS.
  * S3 Access Control.
  * S3 Performance.
  * Amazon S3 Glacier.
  * AWS Snow Family.
  * AWS Storage Gateway.
  * VM Import/Export.
  * Disaster Recovery.
  * RTO and RPO.

* Continue practicing:

  * VM Import/Export.
  * SMB File Shares.
  * Storage Gateway.
  * Backup and Restore.
  * Hybrid Cloud Storage.

---

