
---
title: "Week 4 Worklog"
date: 2026-05-17
weight: 1
chapter: false
pre: " <b> 1.4. </b> "

---

## Week 4 Objectives

* Study the first part of Module 03 about AWS Compute services and virtual servers.
* Understand the architecture, components, and lifecycle of Amazon EC2.
* Distinguish between EC2 Instance types, pricing models, and use cases.
* Learn about Amazon Machine Images, Key Pairs, and EC2 backup methods.
* Practice managing Amazon EBS, Snapshots, and Instance Store.
* Deploy a basic application on EC2 and become familiar with automated server initialization.
* Organize resources using AWS Tags and Resource Groups.
* Become familiar with Infrastructure as Code using AWS CloudFormation.
* Configure EC2 monitoring using Amazon CloudWatch.
* Develop troubleshooting skills related to EC2, storage, access permissions, and monitoring.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Studied Module 03-01 – Compute VMs on AWS <br> - Learned about the role of Compute services on AWS <br> - Distinguished between physical servers, virtual machines, and Cloud Compute models <br> - Reviewed the main AWS Compute services | 11/05/2026 | 11/05/2026 | https://www.youtube.com/watch?v=-t5h4N6vfBs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=72 |
| 2 | - Studied Module 03-01-01 about Amazon EC2 <br> - Learned about EC2 Instance Types, the Instance lifecycle, and pricing models <br> - Analyzed how to select an EC2 configuration based on workload requirements | 12/05/2026 | 12/05/2026 | https://www.youtube.com/watch?v=e7XeKdOVq40&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=73 |
| 3 | - Studied Module 03-01-02 about AMIs, backups, and Key Pairs <br> - Launched an EC2 Instance <br> - Configured a Security Group and Key Pair <br> - Practiced creating an AMI from an Instance | 13/05/2026 | 13/05/2026 | https://www.youtube.com/watch?v=yAR6QRT3N1k&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=74, https://000004.awsstudygroup.com/vi/ |
| 4 | - Studied Module 03-01-03 about Amazon Elastic Block Store <br> - Created and attached an EBS Volume to EC2 <br> - Formatted, mounted, and checked the Volume <br> - Created a Snapshot and restored a Volume | 14/05/2026 | 14/05/2026 | https://www.youtube.com/watch?v=hKr_TfGP7NY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=75, https://000004.awsstudygroup.com/vi/ |
| 5 | - Studied Module 03-01-04 about EC2 Instance Store <br> - Compared Instance Store with Amazon EBS <br> - Tested data durability <br> - Configured Tags and organized resources using Resource Groups | 15/05/2026 | 15/05/2026 | https://www.youtube.com/watch?v=6IHNDJ85aoQ&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=76, https://000027.awsstudygroup.com/vi/ |
| 6 | - Continued practicing AWS Tags and Resource Groups <br> - Organized resources by Environment, Owner, and Purpose <br> - Became familiar with the structure of a CloudFormation Template <br> - Checked resources by CloudFormation Stack | 16/05/2026 | 16/05/2026 | https://000027.awsstudygroup.com/vi/ |
| 7 | - Deployed an AWS CloudFormation Stack <br> - Monitored EC2 using CloudWatch Metrics <br> - Practiced Search Expressions and Math Expressions <br> - Configured CloudWatch Logs, Metric Filters, Alarms, and Dashboards | 17/05/2026 | 17/05/2026 | https://000008.awsstudygroup.com/vi/ |

---

## Week 4 Outcomes

### 1. Completed the First Part of Module 03

The following topics were studied:

| Module | Content |
| --- | --- |
| Module 03-01 | Overview of Compute VMs on AWS |
| Module 03-01-01 | Amazon Elastic Compute Cloud |
| Module 03-01-02 | AMIs, Backups, and Key Pairs |
| Module 03-01-03 | Amazon Elastic Block Store |
| Module 03-01-04 | EC2 Instance Store |

Through this part of the module, I learned how AWS provides virtual server resources, how to select Compute configurations, and how to manage storage attached to EC2.

---

### 2. Overview of AWS Compute Services

Amazon EC2 allows users to provision virtual servers on demand without directly managing physical hardware infrastructure.

Basic deployment process:

```text
Select an Amazon Machine Image
          ↓
Select an Instance Type
          ↓
Select a VPC and Subnet
          ↓
Attach Storage
          ↓
Configure a Security Group
          ↓
Select a Key Pair
          ↓
Launch an EC2 Instance
```

Main benefits:

* Provision resources on demand.
* Change configurations flexibly.
* Support multiple operating systems.
* Integrate with VPC, IAM, EBS, and CloudWatch.
* Scale automatically according to workload demand.
* Pay based on the selected resource type and usage duration.

---

### 3. Amazon EC2 Architecture and Lifecycle

The main EC2 states include:

```text
Pending
   ↓
Running
   ↓
Stopping
   ↓
Stopped
   ↓
Shutting-down
   ↓
Terminated
```

Understood that:

* `Pending`: AWS is preparing the required resources.
* `Running`: The Instance is operating.
* `Stopping`: The Instance is being stopped.
* `Stopped`: The Instance is not running, but some storage resources may still exist.
* `Terminated`: The Instance has been deleted and cannot be restarted.

Stopping an Instance does not mean that all costs stop because EBS Volumes, Snapshots, and Elastic IPs may continue to exist and generate charges.

---

### 4. EC2 Instance Types

The following Instance Type categories were studied:

| Category | Use Case |
| --- | --- |
| General Purpose | Web applications, development servers, and balanced workloads |
| Compute Optimized | Compute-intensive processing, batch processing, and high-performance computing |
| Memory Optimized | In-memory databases and workloads requiring large amounts of RAM |
| Storage Optimized | Systems requiring high read and write performance |
| Accelerated Computing | Machine Learning, graphics processing, and GPU-based workloads |

When selecting an Instance Type, the following factors should be considered:

* Number of vCPUs.
* Amount of RAM.
* Network performance.
* Storage type.
* CPU architecture.
* Operational cost.
* Future scalability requirements.

---

### 5. EC2 Pricing Models

#### On-Demand Instances

* Payment is based on actual usage.
* No long-term commitment is required.
* Suitable for short-term or unpredictable workloads.

#### Reserved Instances and Savings Plans

* Require a usage commitment.
* Can reduce costs for stable workloads.
* Suitable for systems that operate continuously over a long period.

#### Spot Instances

* Use spare EC2 capacity.
* Offer lower prices.
* Can be interrupted by AWS.
* Suitable for interruption-tolerant workloads.

---

### 6. Amazon Machine Image

An AMI is a template used to launch EC2 Instances.

An AMI can contain:

* An operating system.
* Installed software.
* Application configurations.
* Root Volume information.
* Block Device Mapping.
* Image permissions.

AMI creation process:

```text
Configure an EC2 Instance
        ↓
Verify the Application
        ↓
Create an Image
        ↓
Create Related Snapshots
        ↓
Use the AMI to Launch New Instances
```

Benefits:

* Standardizes server configurations.
* Deploys multiple identical Instances.
* Reduces installation time.
* Supports backup and disaster recovery.
* Can be used with Launch Templates and Auto Scaling.

---

### 7. Key Pairs and EC2 Access

A Key Pair is used for authentication when connecting to EC2.

For Linux:

* The Private Key is used for SSH connections.
* The Public Key is stored on the Instance.

For Windows:

* The Private Key is used to decrypt the Administrator password.
* The user then connects using Remote Desktop.

Security principles:

* Do not share the Private Key.
* Restrict read permissions on the Key file.
* Do not store the Key in source code.
* Open SSH or RDP ports only to necessary IP addresses.
* Prefer Session Manager in environments with higher security requirements.

---

### 8. Amazon Elastic Block Store

Amazon EBS provides persistent Block Storage for EC2.

Completed the following tasks:

* Created an EBS Volume.
* Attached the Volume to EC2.
* Identified the device name.
* Created a File System.
* Mounted the Volume.
* Wrote test data.
* Created a Snapshot.
* Restored a Volume from a Snapshot.

Practice flow:

```text
Create EBS Volume
        ↓
Attach to EC2
        ↓
Format File System
        ↓
Mount Volume
        ↓
Store Data
        ↓
Create Snapshot
```

---

### 9. EBS Volume Types

Common Volume types:

| Type | Purpose |
| --- | --- |
| gp3 | General-purpose SSD suitable for most workloads |
| gp2 | Previous-generation general-purpose SSD |
| io1/io2 | Workloads requiring high and consistent IOPS |
| st1 | HDD optimized for high throughput |
| sc1 | Low-cost HDD for infrequently accessed data |

Factors to consider:

* Capacity.
* IOPS.
* Throughput.
* Latency.
* Encryption capability.
* Data importance.
* Cost.

---

### 10. Snapshots and Backups

A Snapshot is a point-in-time copy of an EBS Volume.

Understood that:

* Snapshots are stored in AWS-managed storage.
* The first Snapshot contains all necessary data.
* Subsequent Snapshots operate incrementally.
* A Snapshot can be used to create a new Volume.
* Snapshots can be copied to another Region.
* Snapshots can support Disaster Recovery processes.

Comparison:

| Component | Role |
| --- | --- |
| EBS Volume | Block Storage currently used by EC2 |
| Snapshot | Point-in-time copy of EBS data |
| AMI | Template for deploying EC2 Instances |
| AWS Backup | Centralized Backup management service |
| Instance Store | Temporary storage attached to the physical host |

---

### 11. EC2 Instance Store

Instance Store is temporary storage physically attached to the host running the EC2 Instance.

Characteristics:

* Provides high performance.
* Suitable for temporary data.
* Data is not guaranteed to persist.
* Data may be lost when the Instance is stopped, terminated, or moved to another host.
* Cannot be detached and attached to another Instance like EBS.

Use cases:

* Cache.
* Buffers.
* Intermediate data.
* Temporary processing.
* Data that can be regenerated.

Instance Store should not be used as the only location for important data.

---

### 12. AWS Tags and Resource Groups

Tags are created as Key–Value pairs.

Example:

```text
Environment = Development
Owner       = Tier-S-Team
Project     = FCJ-Management
Purpose     = Web-Server
```

Benefits:

* Organize resources.
* Search and filter resources.
* Categorize costs.
* Identify resource owners.
* Support automation.
* Control access based on Tags.

Resource Groups allow resources with the same Tags or belonging to the same CloudFormation Stack to be grouped together.

---

### 13. Infrastructure as Code with CloudFormation

CloudFormation allows infrastructure to be described using Templates.

General structure:

```text
Template
   ↓
CloudFormation Stack
   ↓
AWS Resources
```

Completed the following tasks:

* Created a Stack.
* Validated a Template.
* Monitored Stack Events.
* Checked the created resources.
* Updated the Stack.
* Deleted the Stack and related resources.

Benefits:

* Repeatable deployment.
* Reduced manual configuration errors.
* Version-controlled infrastructure.
* Consistent configuration across environments.

---

### 14. Monitoring with Amazon CloudWatch

The following components were practiced:

* CloudWatch Metrics.
* CloudWatch Logs.
* Metric Filters.
* CloudWatch Alarms.
* CloudWatch Dashboards.
* Search Expressions.
* Math Expressions.

Common EC2 Metrics:

* CPUUtilization.
* NetworkIn.
* NetworkOut.
* DiskReadOps.
* DiskWriteOps.
* StatusCheckFailed.

CloudWatch helps monitor operations, detect abnormal behavior, and support troubleshooting.

---

## Practical Issues Resolved

### 1. Unable to Connect to EC2

The following elements were checked:

* Instance State.
* Public IP or Private IP.
* Route Table.
* Internet Gateway.
* Security Group.
* Network ACL.
* Key Pair.
* Private Key permissions.
* SSH or RDP Service.

---

### 2. EBS Volume Did Not Appear in the Operating System

The following elements were checked:

* The Volume and Instance were in the same Availability Zone.
* Attachment status.
* Device name.
* File System.
* Mount Point.
* `/etc/fstab` when automatic mounting was required.

Commands used:

```bash
lsblk
df -h
sudo file -s /dev/xvdf
```

---

### 3. Unable to Create an AMI or Snapshot

The following possible causes were reviewed:

* Missing IAM permissions.
* The EBS Volume had active write operations.
* The KMS Key did not allow access.
* The Snapshot was still in the Pending state.
* The AMI depended on a Snapshot that had not completed.

---

### 4. CloudFormation Stack Deployment Failed

Troubleshooting process:

* Checked Stack Events.
* Identified the first Resource that failed.
* Checked IAM permissions.
* Checked whether the resource name already existed.
* Checked the Region and Availability Zone.
* Validated the Template syntax.
* Reviewed dependencies between resources.

---

### 5. CloudWatch Did Not Display the Expected Data

The following possible causes were checked:

* Incorrect Namespace.
* Incorrect Metric Name.
* Incorrect Dimension.
* No data existed in the selected time range.
* The selected Period was not appropriate.
* The CloudWatch Agent had not submitted Custom Metrics.
* The Search Expression syntax was incorrect.

---

## Skills Developed

* Understanding EC2 architecture and lifecycle.
* Selecting Instance Types according to workload requirements.
* Distinguishing between EC2 pricing models.
* Creating and using AMIs.
* Managing Key Pairs.
* Creating, attaching, and mounting EBS Volumes.
* Creating and restoring Snapshots.
* Distinguishing between EBS and Instance Store.
* Organizing resources using Tags.
* Deploying CloudFormation Stacks.
* Monitoring resources using CloudWatch.
* Troubleshooting EC2, storage, and monitoring issues.

---

## Self-Evaluation

* Built a foundational understanding of Amazon EC2 through Module 03.
* Understood the relationship between EC2, AMIs, EBS, Snapshots, and Instance Store.
* Able to launch and manage a basic EC2 Instance.
* Able to attach additional Storage and create data copies.
* Able to organize resources using Tags and Resource Groups.
* Understood the initial roles of CloudFormation and CloudWatch.
* Improved the ability to troubleshoot issues based on individual components.

Areas for further improvement:

* Practice more with EC2 Metadata and User Data.
* Develop a deeper understanding of EBS encryption.
* Practice copying AMIs between Regions.
* Standardize CloudFormation Templates.
* Install the CloudWatch Agent to collect Memory and Disk Metrics.
* Study Auto Scaling and High Availability in more detail.

---

## Next Steps

* Continue studying the remaining parts of Module 03:

  * EC2 User Data.
  * EC2 Metadata.
  * EC2 Auto Scaling.
  * Amazon EFS.
  * Amazon FSx.
  * Amazon Lightsail.
  * AWS Application Migration Service.

* Practice:

  * Launch Templates.
  * Target Groups.
  * Application Load Balancers.
  * Auto Scaling Groups.
  * Dynamic Scaling.
  * Scheduled Scaling.
  * Predictive Scaling.
  * CloudWatch Custom Metrics.

---
