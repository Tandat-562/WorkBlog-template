---
title: "Week 5 Worklog"
date: 2026-05-24
weight: 1
chapter: false
pre: " <b> 1.5. </b> "

---

## Week 5 Objectives

* Complete the remaining sections of Module 03 about AWS Compute services.
* Study EC2 User Data and EC2 Instance Metadata.
* Understand the process of automating server configuration during initialization.
* Study the architecture of EC2 Auto Scaling and Elastic Load Balancing.
* Practice using Launch Templates, Target Groups, Load Balancers, and Auto Scaling Groups.
* Distinguish between Manual, Scheduled, Dynamic, and Predictive Scaling.
* Learn about Amazon EFS, Amazon FSx, and File Storage systems.
* Practice deploying applications using Amazon Lightsail.
* Study the fundamentals of AWS Application Migration Service.
* Develop monitoring, scaling, and troubleshooting skills in highly available systems.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Studied Module 03-01-05 about EC2 User Data <br> - Wrote a Startup Script to install a Web Server <br> - Checked Cloud-Init Logs <br> - Reviewed AMIs, EBS, and Snapshots | 05/18/2026 | 05/18/2026 | https://www.youtube.com/watch?v=_v_43Wi7zjo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=77 |
| 2 | - Studied Module 03-01-06 about EC2 Metadata <br> - Retrieved the Instance ID, Region, Private IP, and Security Credentials <br> - Learned about Instance Metadata Service v1 and v2 <br> - Reviewed CloudWatch Metrics and Logs | 05/19/2026 | 05/19/2026 | https://www.youtube.com/watch?v=Ew3QRaKJQSA&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=78 |
| 3 | - Studied Module 03-01-07 about EC2 Auto Scaling <br> - Learned about Launch Templates, Auto Scaling Groups, and Scaling Policies <br> - Analyzed Minimum, Desired, and Maximum Capacity <br> - Reviewed Security Groups and EC2 Networking | 05/20/2026 | 05/20/2026 | https://www.youtube.com/watch?v=bbLcPitXJSY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=79 |
| 4 | - Studied Module 03-02 about EC2 Auto Scaling, EFS, FSx, Lightsail, and MGN <br> - Compared Block Storage with File Storage <br> - Studied server migration options for AWS | 05/21/2026 | 05/21/2026 | https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80 |
| 5 | - Deployed a Launch Template <br> - Created a Target Group and Application Load Balancer <br> - Created an Auto Scaling Group <br> - Prepared CloudWatch Custom Metrics | 05/22/2026 | 05/22/2026 | https://000006.awsstudygroup.com/vi/ |
| 6 | - Continued the Auto Scaling Lab <br> - Practiced Manual, Scheduled, Dynamic, and Predictive Scaling <br> - Checked Health Checks and traffic distribution <br> - Monitored Scaling Activities | 05/23/2026 | 05/23/2026 | https://000006.awsstudygroup.com/vi/ |
| 7 | - Deployed an Amazon Lightsail Database <br> - Created WordPress and PrestaShop Instances <br> - Checked Static IP and networking configurations <br> - Resolved Instance Limit and Quota Restriction issues | 05/24/2026 | 05/24/2026 | https://000045.awsstudygroup.com/vi/ |

---

## Week 5 Outcomes

### 1. Completed Module 03

The following content was completed:

| Module | Content |
| --- | --- |
| Module 03-01-05 | EC2 User Data |
| Module 03-01-06 | EC2 Instance Metadata |
| Module 03-01-07 | EC2 Auto Scaling |
| Module 03-02 | Auto Scaling, EFS, FSx, Lightsail, and Application Migration Service |

After two weeks, I completed the entire Module 03 learning sequence covering virtual servers, Compute-related storage, automation, system scaling, and related AWS Compute services.

---

### 2. Automating EC2 with User Data

User Data allows a Script to run when an EC2 Instance is launched.

Example:

```bash
#!/bin/bash
dnf update -y
dnf install httpd -y
systemctl enable httpd
systemctl start httpd
echo "<h1>FCJ Management Server</h1>" > /var/www/html/index.html
```

Execution flow:

```text
Launch EC2
    ↓
Operating System Starts
    ↓
Cloud-Init Reads User Data
    ↓
Install Packages
    ↓
Configure Application
    ↓
Start Services
```

Benefits:

* Reduces manual configuration.
* Standardizes server configurations.
* Supports creating multiple Instances with identical configurations.
* Works well with Launch Templates and Auto Scaling.
* Reduces deployment time.

---

### 3. Troubleshooting User Data

The following elements were checked:

* Script Shebang.
* Root permissions.
* Package Manager.
* Internet connectivity.
* NAT Gateway or Internet Gateway.
* Repository availability.
* Service name.
* Cloud-Init Logs.

Log files:

```bash
/var/log/cloud-init.log
/var/log/cloud-init-output.log
```

Verification commands:

```bash
sudo cat /var/log/cloud-init-output.log
sudo systemctl status httpd
```

Understood that User Data normally runs only during the first initialization unless additional configuration is applied.

---

### 4. EC2 Instance Metadata

Instance Metadata provides information about the currently running EC2 Instance.

Example data:

* Instance ID.
* Instance Type.
* Availability Zone.
* Region.
* Private IP.
* Public IP.
* IAM Role.
* Temporary Credentials.
* Network Interface.

Metadata allows an application to access Instance information without hardcoding it in the source code.

---

### 5. Instance Metadata Service v2

IMDSv2 requires a Session Token before Metadata can be retrieved.

Example:

```bash
TOKEN=$(curl -X PUT \
"http://169.254.169.254/latest/api/token" \
-H "X-aws-ec2-metadata-token-ttl-seconds: 21600")

curl \
-H "X-aws-ec2-metadata-token: $TOKEN" \
http://169.254.169.254/latest/meta-data/instance-id
```

Benefits of IMDSv2:

* Requires a Token.
* Reduces the risk of Metadata exploitation through SSRF.
* Supports Hop Limit restrictions.
* Provides stronger security than IMDSv1.

Temporary Credentials retrieved from Metadata should not be written to Logs or shared outside the Instance.

---

### 6. EC2 Auto Scaling Architecture

The main components include:

```text
Launch Template
       ↓
Auto Scaling Group
       ↓
EC2 Instances
       ↓
Target Group
       ↓
Application Load Balancer
       ↓
Users
```

An Auto Scaling Group maintains the number of Instances within the configured range:

* Minimum Capacity.
* Desired Capacity.
* Maximum Capacity.

When an Instance fails a Health Check, Auto Scaling can replace it.

---

### 7. Launch Templates

A Launch Template stores the configuration used to create EC2 Instances:

* AMI.
* Instance Type.
* Key Pair.
* Security Group.
* IAM Instance Profile.
* Storage.
* User Data.
* Network Configuration.
* Tags.

Comparison:

| AMI | Launch Template |
| --- | --- |
| Contains the operating system and software | Contains EC2 deployment settings |
| Used as the source Image | References an AMI |
| Can be created from an EC2 Instance | Can have multiple Versions |
| Does not define Scaling behavior | Used by an Auto Scaling Group |

---

### 8. Elastic Load Balancing

An Application Load Balancer distributes HTTP/HTTPS traffic across multiple Targets.

Traffic flow:

```text
Client
   ↓
Application Load Balancer
   ↓
Target Group
   ↓
Healthy EC2 Instances
```

Main components:

* Listener.
* Listener Rule.
* Target Group.
* Health Check.
* Registered Targets.
* Security Group.

The Load Balancer only sends traffic to Targets that are considered Healthy.

---

### 9. Target Groups and Health Checks

A Target Group manages the list of Backend Targets.

A Health Check can verify:

* Protocol.
* Port.
* Path.
* Interval.
* Timeout.
* Healthy Threshold.
* Unhealthy Threshold.
* Expected Status Code.

Possible reasons for an Unhealthy Target:

* The Web Server is not running.
* The Health Check Path is incorrect.
* A Security Group blocks traffic.
* The application returns an unexpected Status Code.
* The Target Group uses the wrong Port.
* User Data has not completed.
* A Route or NACL is configured incorrectly.

---

### 10. Scaling Methods

#### Manual Scaling

An Administrator manually changes the Desired Capacity.

#### Scheduled Scaling

Capacity changes according to a predefined schedule.

Example:

```text
08:00 – Increase to 4 Instances
22:00 – Decrease to 1 Instance
```

#### Dynamic Scaling

Capacity changes according to real-time Metrics.

Examples:

* Target Tracking.
* Step Scaling.
* Simple Scaling.

#### Predictive Scaling

Historical data is used to forecast future demand and prepare Capacity before traffic increases.

---

### 11. CloudWatch Custom Metrics

Custom Metrics are used when the default Metrics do not fully represent the workload.

Examples:

* Number of Requests.
* Queue length.
* Number of active Users.
* Number of pending Jobs.
* Application Latency.

Example of submitting a Metric using AWS CLI:

```bash
aws cloudwatch put-metric-data \
  --namespace FCJManagement \
  --metric-name ActiveUsers \
  --value 25 \
  --unit Count
```

A Custom Metric can be used with a CloudWatch Alarm and Scaling Policy.

---

### 12. Amazon EFS

Amazon EFS provides managed File Storage using NFS.

Characteristics:

* Multiple EC2 Instances can mount the same File System.
* Storage capacity scales automatically.
* Mount Targets can be deployed across multiple Availability Zones.
* Suitable for Linux workloads.
* Supports shared data storage.

Use cases:

* Shared Web Content.
* Content Management Systems.
* Home Directories.
* Shared Application Data.
* Container Storage.

---

### 13. Amazon FSx

Amazon FSx provides managed File Storage systems.

Available options include:

| Service | Use Case |
| --- | --- |
| FSx for Windows File Server | Windows workloads, SMB, and Active Directory |
| FSx for Lustre | High-performance computing and Machine Learning |
| FSx for NetApp ONTAP | Enterprise workloads and Data Management |
| FSx for OpenZFS | Workloads requiring ZFS capabilities |

The appropriate option depends on the operating system, protocol, performance requirements, and integration needs.

---

### 14. Amazon Lightsail

Lightsail provides a simplified deployment environment with predictable bundle-based pricing.

Completed the following tasks:

* Created a Linux Instance.
* Created a WordPress Instance.
* Created a PrestaShop Instance.
* Created a Lightsail Database.
* Assigned a Static IP.
* Checked Firewall settings.
* Monitored Metrics.
* Deleted resources after completing the exercises.

Lightsail is suitable for:

* Small websites.
* Blogs.
* Demonstrations.
* Development environments.
* Applications that do not require complex AWS architectures.

---

### 15. AWS Application Migration Service

AWS Application Migration Service supports server migration to AWS.

General process:

```text
Source Server
      ↓
Install Replication Agent
      ↓
Replicate Data to AWS
      ↓
Launch Test Instance
      ↓
Validate Application
      ↓
Perform Cutover
      ↓
Launch Production Instance
```

Benefits:

* Reduces downtime.
* Supports testing before Cutover.
* Automates the Replication process.
* Suitable for the Rehost migration strategy.

---

### 16. High Availability and Resilience

Deployment model:

```text
                 Internet
                    ↓
       Application Load Balancer
              /             \
     Availability Zone A   Availability Zone B
             ↓                    ↓
        EC2 Instance          EC2 Instance
              \               /
               Auto Scaling Group
```

Benefits:

* Avoids dependence on a single Instance.
* Replaces failed Instances.
* Distributes traffic across multiple Availability Zones.
* Adjusts Capacity automatically.
* Improves Availability and Fault Tolerance.

---

## Practical Issues Resolved

### 1. User Data Could Not Install the Application

The following possible causes were checked:

* Script syntax errors.
* The Instance did not have Internet access.
* The Repository could not be reached.
* The wrong Package Manager was used.
* The Service Name was incorrect.
* User Data was not running with Root permissions.
* The Script depended on resources that were not ready.

---

### 2. Load Balancer Target Was Unhealthy

Resolution steps:

* Checked the application on EC2.
* Checked the Port.
* Checked the Health Check Path.
* Checked the EC2 Security Group.
* Allowed traffic from the Load Balancer Security Group.
* Checked the returned Status Code.
* Reviewed User Data and application Logs.

---

### 3. Auto Scaling Did Not Launch an Instance

The following possible causes were reviewed:

* Incorrect Launch Template configuration.
* The AMI did not exist.
* Insufficient IAM permissions.
* The Instance Type was unavailable.
* The Service Quota had been exceeded.
* The Subnet did not have enough IP addresses.
* The Key Pair or Security Group was incorrect.
* User Data caused initialization errors.

---

### 4. Predictive Scaling Did Not Have Enough Data

Understood that:

* Predictive Scaling requires historical Metric data.
* The Metric must have a clear pattern and trend.
* Custom Metrics must be submitted consistently.
* Namespace and Dimensions must remain consistent.
* Predictive Scaling should not be evaluated after only a short period.

---

### 5. AWS CLI Could Not Submit a Custom Metric

The following elements were checked:

* AWS CLI Profile.
* Region.
* IAM permissions.
* Namespace.
* Metric Name.
* Unit.
* Credentials.
* System time.

---

### 6. Lightsail Could Not Create Additional Instances

The following possible causes were checked:

* Lightsail Instance Limit.
* Account restrictions.
* Region availability.
* Blueprint.
* Bundle.
* Service Quota.
* Billing or account verification.

The actual Lightsail limits may differ from some displayed Service Quotas. An AWS Support Case may be required to verify account-specific restrictions.

---

### 7. The Stress Test Was Not Fully Completed

Limitations:

* The intended load-testing tool was not successfully downloaded and configured.
* Stable traffic could not be generated to observe the entire Scaling Activity.

Results still achieved:

* Understood the Scale-out and Scale-in processes.
* Monitored Health Checks.
* Analyzed Metrics used for Scaling.
* Understood how the Load Balancer works with the Auto Scaling Group.

---

## Skills Developed

* Writing EC2 User Data Scripts.
* Checking Cloud-Init Logs.
* Retrieving EC2 Metadata using IMDSv2.
* Creating Launch Templates.
* Configuring Target Groups and Load Balancers.
* Creating Auto Scaling Groups.
* Distinguishing between Scaling methods.
* Submitting CloudWatch Custom Metrics.
* Understanding Amazon EFS and Amazon FSx.
* Deploying applications using Lightsail.
* Understanding the migration process with AWS MGN.
* Troubleshooting Monitoring, Scaling, and High Availability issues.

---

## Self-Evaluation

* Completed all content in Module 03.
* Understood how to automate the EC2 initialization process.
* Learned how to use Metadata without hardcoding Instance information.
* Understood the roles of Launch Templates, Load Balancers, and Auto Scaling Groups.
* Distinguished between Manual, Scheduled, Dynamic, and Predictive Scaling.
* Understood the differences between EBS, EFS, FSx, and Instance Store.
* Able to deploy a basic application using Amazon Lightsail.
* Improved troubleshooting skills for multi-component architectures.

Areas for further improvement:

* Practice Auto Scaling with real traffic.
* Study Scaling Cooldown and Instance Warmup in greater depth.
* Practice configuring HTTPS Listeners and AWS Certificate Manager.
* Study EFS Performance Modes and Throughput Modes.
* Practice FSx for Windows with Active Directory.
* Practice migration using AWS Application Migration Service.
* Optimize Load Balancer and Auto Scaling costs.

---

## Next Steps

* Begin Module 04 about AWS Storage Services.
* Study:

  * Amazon S3.
  * S3 Storage Classes.
  * S3 Versioning.
  * S3 Lifecycle.
  * Amazon S3 Glacier.
  * AWS Backup.
  * AWS Storage Gateway.
  * AWS Snow Family.
  * VM Import/Export.

* Continue practicing:

  * Backup and Restore.
  * Disaster Recovery.
  * RTO and RPO.
  * Static Website Hosting.
  * CloudFront.
  * Hybrid Storage.
  * Data lifecycle management.

---

