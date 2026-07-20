
---
title: "Week 7 Worklog"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 1.7. </b> "

---

## Week 7 Objectives

* Complete the remaining content of Module 04.
* Study S3 Static Website Hosting, CORS, and access control methods.
* Understand Object Key organization and Amazon S3 performance optimization.
* Study Amazon S3 Glacier and the process of restoring long-term archived data.
* Learn about the AWS Snow Family and large-scale data migration methods.
* Practice VM Import/Export to migrate virtual machines between on-premises environments and AWS.
* Deploy AWS Storage Gateway using a Hybrid Cloud model.
* Create an SMB File Share connected to Amazon S3.
* Reinforce knowledge of Backup, Restore, Disaster Recovery, RTO, and RPO.
* Improve troubleshooting skills related to storage, migration, and Hybrid Connectivity.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Studied Module 04-03 <br> - Learned about S3 Static Website Hosting, CORS, and Access Control <br> - Analyzed Object Keys, Prefixes, and S3 access performance | 01/06/2026 | 01/06/2026 | https://www.youtube.com/watch?v=mPBjB6Ltl_Q&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=105 |
| 2 | - Studied Module 04-04 <br> - Learned about Amazon S3 Glacier, AWS Snow Family, and Storage Gateway <br> - Analyzed data migration methods for AWS | 02/06/2026 | 02/06/2026 | https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106 |
| 3 | - Practiced Lab 000014 <br> - Prepared a virtual machine Image <br> - Created the `vmimport` IAM Role <br> - Uploaded the Image to S3 and performed a VM Import | 03/06/2026 | 03/06/2026 | https://000014.awsstudygroup.com/vi/ |
| 4 | - Continued the VM Import/Export Lab <br> - Created an AMI from the imported virtual machine <br> - Launched an EC2 Instance from the AMI <br> - Studied the Instance Export and Image Export processes | 04/06/2026 | 04/06/2026 | https://000014.awsstudygroup.com/vi/ |
| 5 | - Practiced Lab 000024 <br> - Deployed AWS Storage Gateway <br> - Activated a File Gateway <br> - Created an SMB File Share using Amazon S3 as the Backend | 05/06/2026 | 05/06/2026 | https://000024.awsstudygroup.com/vi/ |
| 6 | - Connected to the SMB File Share from a Client <br> - Verified that data was synchronized to Amazon S3 <br> - Resolved Gateway and File Share issues <br> - Monitored Cache and connection status | 06/06/2026 | 06/06/2026 | https://000024.awsstudygroup.com/vi/ |
| 7 | - Reviewed the entire Module 04 <br> - Compared S3, Glacier, Snow Family, Storage Gateway, and AWS Backup <br> - Summarized Disaster Recovery strategies <br> - Reviewed and deleted unused resources | 07/06/2026 | 07/06/2026 | https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106 |

---

## Week 7 Outcomes

### 1. Completed Module 04

The following content was completed over two weeks:

| Module | Content |
| --- | --- |
| Module 04-01 | Overview of AWS Storage services |
| Module 04-02 | Amazon S3, Access Points, and Storage Classes |
| Module 04-03 | Static Website Hosting, CORS, Access Control, Object Keys, Performance, and Glacier |
| Module 04-04 | Snow Family, Storage Gateway, and data migration methods |
| Practical Exercises | Amazon S3, AWS Backup, VM Import/Export, and Storage Gateway |

After completing Module 04, I understood the entire data lifecycle, including data creation, storage, access, backup, long-term archiving, migration, and restoration.

---

### 2. S3 Static Website Hosting and CORS

CORS allows an application from one Domain to send Requests to resources on another Domain.

Example:

```text
Frontend: https://app.example.com
        ↓
Request to Amazon S3
        ↓
S3 checks the CORS Configuration
        ↓
Allow or deny the Request
```

A CORS Configuration can define:

* Allowed Origins.
* Allowed Methods.
* Allowed Headers.
* Exposed Headers.
* Max Age.

Example:

```json
[
  {
    "AllowedOrigins": ["https://app.example.com"],
    "AllowedMethods": ["GET"],
    "AllowedHeaders": ["*"],
    "ExposeHeaders": ["ETag"],
    "MaxAgeSeconds": 3000
  }
]
```

Understood that CORS does not replace IAM Policies or Bucket Policies. The Request must still have appropriate access permissions.

---

### 3. Amazon S3 Access Control

The following mechanisms were studied:

* IAM Identity-Based Policies.
* S3 Bucket Policies.
* Access Point Policies.
* ACLs.
* Block Public Access.
* VPC Endpoint Policies.
* KMS Key Policies.
* Pre-Signed URLs.

Permission evaluation process:

```text
Request
   ↓
Authentication
   ↓
IAM Policy
   ↓
Bucket or Access Point Policy
   ↓
Block Public Access
   ↓
KMS Permission when encryption is used
   ↓
Allow or Deny
```

Important principles:

* An Explicit Deny always takes priority.
* Grant only the required permissions.
* Avoid making a Bucket public unless it is necessary.
* CloudFront should be used for public content distribution.
* Use a Pre-Signed URL when temporary access to an Object is required.

---

### 4. Object Keys and Prefixes

Example Object Key:

```text
reports/2026/06/architecture-review.pdf
```

In this example:

* `reports/` is the first-level Prefix.
* `2026/06/` is the next Prefix.
* `architecture-review.pdf` is the filename.

An appropriate Object Key design helps with:

* Organizing data.
* Filtering Objects.
* Applying Lifecycle Rules.
* Controlling permissions by Prefix.
* Analyzing costs.
* Supporting application data searches.

---

### 5. Amazon S3 Performance

The following methods were studied:

* Use Multipart Upload for large files.
* Use Byte-Range Fetch.
* Use Transfer Acceleration when uploading from distant locations.
* Use CloudFront for content distribution.
* Perform Requests in parallel.
* Use an SDK with Retry and Exponential Backoff.
* Monitor `4xx` and `5xx` errors.
* Select a Region close to the application and users.

Multipart Upload flow:

```text
Large File
   ↓
Split into Parts
   ↓
Upload Parts in Parallel
   ↓
Complete Multipart Upload
   ↓
Amazon S3 Object
```

---

### 6. Amazon S3 Glacier

Glacier is used for long-term data storage.

Use cases:

* Legal records.
* Compliance data.
* Long-term backups.
* Media archives.
* Infrequently accessed data.
* Disaster Recovery copies.

When using Glacier, the following factors should be considered:

* Retrieval time.
* Retrieval cost.
* Minimum Storage Duration.
* Frequency of data access.
* RTO requirements.

A Lifecycle Rule can automatically transition data from S3 Standard to Glacier.

---

### 7. AWS Snow Family

AWS Snow Family supports data migration when:

* The volume of data is extremely large.
* Internet bandwidth is limited.
* Network connectivity is unstable.
* Network data transfer costs are high.
* Internet transfer time does not meet requirements.

The following devices were studied:

| Device | Use Case |
| --- | --- |
| AWS Snowcone | Small-scale data migration and Edge Computing |
| AWS Snowball Edge | Large-scale data migration and Edge processing |
| AWS Snowmobile | Extremely large-scale data migration |

General process:

```text
Create a Snow Job
     ↓
AWS ships the device
     ↓
Copy data to the device
     ↓
Return the device to AWS
     ↓
AWS imports the data
     ↓
Data becomes available in Amazon S3
```

---

### 8. VM Import/Export

VM Import/Export supports migrating virtual machines from an existing environment to AWS.

Import process:

```text
On-Premises Virtual Machine
          ↓
Export Virtual Disk
          ↓
Upload Image to Amazon S3
          ↓
VM Import/Export Service
          ↓
Create Amazon Machine Image
          ↓
Launch EC2 Instance
```

Required components:

* Virtual machine Image.
* S3 Bucket.
* `vmimport` IAM Role.
* Trust Policy.
* Service Role Permissions.
* Import Task.
* AMI.
* EC2 Instance.

---

### 9. IAM Role for VM Import/Export

The `vmimport` Role allows the service to:

* Read an Image from Amazon S3.
* Write related data.
* Create Snapshots.
* Create AMIs.
* Perform Import or Export operations.

Common issues:

* Incorrect Role name.
* The Trust Policy does not allow the VM Import/Export service.
* The Role lacks S3 permissions.
* Incorrect Bucket Name.
* Unsupported Image Format.
* The S3 Bucket and Import Task use incompatible Regions.

---

### 10. AWS Storage Gateway

Storage Gateway connects on-premises systems to AWS Storage services.

Architecture:

```text
On-Premises Client
        ↓
SMB or NFS
        ↓
Storage Gateway
        ↓
Local Cache
        ↓
Amazon S3
```

The following Gateway types were studied:

* Amazon S3 File Gateway.
* Amazon FSx File Gateway.
* Volume Gateway.
* Tape Gateway.

Benefits:

* Applications can continue using traditional File protocols.
* Data is stored on AWS.
* Supports Hybrid Cloud architectures.
* Uses a Local Cache to improve access speed.
* Supports Backup and Archive workloads.

---

### 11. File Gateway and SMB File Share

Completed the following tasks:

* Deployed a Gateway Appliance.
* Activated the Gateway.
* Attached a Local Cache Disk.
* Selected an S3 Bucket.
* Created an SMB File Share.
* Configured Guest Access or Authentication.
* Connected to the File Share from a Client.
* Created and modified files.
* Verified Objects in Amazon S3.

Data flow:

```text
Windows Client
      ↓
SMB File Share
      ↓
File Gateway
      ↓
Amazon S3 Object
```

---

### 12. Local Cache in Storage Gateway

The Local Cache stores frequently accessed data.

Benefits:

* Reduces latency.
* Reduces repeated downloads from AWS.
* Improves the experience of on-premises applications.
* Allows Cloud Storage to be used through a File Storage interface.

The following items should be monitored:

* Cache capacity.
* Cache Hits.
* Cache Misses.
* Gateway Health.
* Network Throughput.
* Upload Buffer when required by the Gateway type.

---

### 13. Backup and Restore

Backup process:

```text
Production Resource
        ↓
Backup Plan
        ↓
Backup Job
        ↓
Recovery Point
        ↓
Backup Vault
```

Restore process:

```text
Recovery Point
        ↓
Restore Job
        ↓
New Resource
        ↓
Validation
        ↓
Return to Operation
```

A Backup is only valuable when the data can be restored and validated successfully.

---

### 14. Disaster Recovery

The following strategies were studied:

#### Backup and Restore

* Lower cost.
* Longer recovery time.
* Suitable for systems that do not require immediate restoration.

#### Pilot Light

* Maintains core components on AWS.
* Expands the system when a failure occurs.

#### Warm Standby

* Maintains a smaller running version of the system.
* Can be scaled quickly when required.

#### Multi-Site Active-Active

* The system operates across multiple locations.
* Provides a low RTO.
* Has higher cost and complexity.

---

### 15. Recovery Time Objective and Recovery Point Objective

#### Recovery Time Objective

The maximum period that a system is allowed to remain unavailable.

#### Recovery Point Objective

The maximum amount of data loss that can be accepted, measured in time.

Example:

```text
RTO = 2 hours
RPO = 15 minutes
```

This means:

* The system must be restored within two hours.
* A maximum of 15 minutes of data loss is acceptable.

Backup frequency directly affects RPO, while the recovery architecture affects RTO.

---

## Practical Issues Resolved

### 1. VM Import Task Failed

The following elements were checked:

* Image Format.
* S3 Bucket.
* Object Key.
* `vmimport` IAM Role.
* Trust Relationship.
* Service Permissions.
* Region.
* Import Task Logs.

---

### 2. Unable to Launch EC2 from the Imported AMI

The following possible causes were reviewed:

* The AMI was not yet in the `Available` state.
* The Snapshot had not completed.
* Operating system drivers were not compatible.
* The Boot Mode was incompatible.
* The selected Instance Type was not supported.
* The operating system Network Configuration was incorrect.

---

### 3. Storage Gateway Could Not Be Activated

The following components were checked:

* The Gateway VM was running.
* Network Connectivity.
* DNS Resolution.
* NTP and system time.
* Activation Key.
* Region.
* Security Group.
* Internet connectivity or VPC Endpoints.

---

### 4. SMB File Share Was Unavailable

The following possible causes were checked:

* The Gateway was not in the `Running` state.
* The IAM Role did not have sufficient S3 permissions.
* The S3 Bucket did not exist.
* The File Share Configuration was incorrect.
* Network Connectivity was interrupted.
* Authentication was incorrect.
* The Local Cache Disk had not been configured.

---

### 5. Client Could Not Connect to the SMB Share

The following items were checked:

* Gateway address.
* File Share name.
* TCP Port 445.
* Windows Firewall.
* Security Group.
* Routing.
* DNS.
* Username and Password.
* Guest Access.

Example:

```text
\\gateway-ip\share-name
```

---

### 6. Data Did Not Appear in Amazon S3

The following possible causes were reviewed:

* The file had not been completely closed.
* The Gateway had not completed the Upload.
* The Cache had not been synchronized.
* The IAM Role lacked permissions.
* The Bucket or Prefix was incorrect.
* Network connectivity was interrupted.
* A Cache Refresh was required after data was modified directly in S3.

---

## Skills Developed

* Configuring S3 CORS.
* Analyzing Amazon S3 access control mechanisms.
* Organizing Objects using Keys and Prefixes.
* Understanding S3 performance optimization methods.
* Selecting an appropriate Glacier Storage Class.
* Distinguishing between AWS Snow Family devices.
* Performing VM Import/Export.
* Creating IAM Roles for migration services.
* Deploying AWS Storage Gateway.
* Creating and using SMB File Shares.
* Analyzing Backup, Restore, RTO, and RPO.
* Troubleshooting Hybrid Storage issues.

---

## Self-Evaluation

* Completed all content in Module 04.
* Understood the complete data lifecycle on AWS.
* Able to select a storage service based on requirements.
* Able to deploy a Static Website and manage Amazon S3 access permissions.
* Understood the long-term archiving process using Glacier.
* Understood data migration options using the AWS Snow Family.
* Able to perform the basic steps of VM Import/Export.
* Able to deploy a File Gateway and SMB File Share.
* Developed a stronger understanding of Backup, Restore, and Disaster Recovery.
* Improved troubleshooting skills related to IAM, networking, and storage.

Areas for further improvement:

* Practice S3 Cross-Region Replication.
* Study Object Lock and Legal Hold.
* Practice restoring data from Glacier.
* Study AWS DataSync and AWS Transfer Family.
* Practice Storage Gateway integration with Active Directory.
* Perform a complete Disaster Recovery test.
* Measure actual RTO and RPO values.

---

## Next Steps

* Prepare for the next Module.
* Continue studying:

  * AWS IAM.
  * IAM Policies.
  * IAM Roles.
  * Permission Boundaries.
  * AWS Organizations.
  * IAM Identity Center.
  * AWS KMS.
  * AWS Security Hub.

* Continue applying storage knowledge to projects:

  * Store uploaded files in Amazon S3.
  * Manage reports in Amazon S3.
  * Create Backup Plans.
  * Build Lifecycle Rules.
  * Design Disaster Recovery solutions.
  * Protect data using encryption and Least Privilege.

---

