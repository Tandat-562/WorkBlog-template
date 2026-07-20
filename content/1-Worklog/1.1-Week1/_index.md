---
title: "Week 1 Worklog"
date: 2026-04-18
weight: 1
chapter: false
pre: " <b> 1.1. </b> "

---

## Week 1 Objectives

* Become familiar with the learning environment, communication methods, and working practices within the First Cloud AI Journey community.
* Build an initial foundation in Cloud Computing and the AWS service ecosystem.
* Learn how to set up a secure AWS account, monitor resource usage, and prevent unexpected costs.

---

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Joined the FCAJ community <br> - Introduced myself and communicated with other members <br> - Learned about the study methods and activity milestones of the program | 18/04/2026 | 18/04/2026 | |
| 2 | - Studied an overview of AWS <br>  + Cloud Computing <br>  + AWS Global Infrastructure <br>  + AWS service categories | 19/04/2026 | 19/04/2026 | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 3 | - Registered a personal AWS account <br> - Verified payment information using a Visa card <br> - Recorded the suspended account issue and opened a Support Case | 20/04/2026 | 20/04/2026 | |
| 4 | - Prepared and submitted account verification documents <br> - Responded to emails from AWS Support <br> - Updated the Account Reinstatement status | 21/04/2026 | 21/04/2026 | |
| 5 | - Studied IAM <br> - Created an Admin Group and IAM User <br> - Enabled MFA using Authy | 22/04/2026 | 22/04/2026 | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 6 | - Studied AWS Billing <br> - Created Budgets for Cost, Usage, Reserved Instances, and Savings Plans <br> - Configured alerts | 23/04/2026 | 23/04/2026 | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 7 | - Practiced with Amazon EC2 <br>  + Launched an Instance <br>  + Observed the Instance lifecycle <br>  + Terminated the Instance | 24/04/2026 | 24/04/2026 | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 8 | - Practiced with Amazon RDS <br>  + Created a Database <br>  + Learned about backups and costs | 25/04/2026 | 25/04/2026 | https://www.youtube.com/watch?v=AQlsd0nWdZk |
| 9 | - Completed the two remaining tasks using AWS Lambda and Amazon Bedrock <br> - Checked the completion status of the five AWS Credit Tasks <br> - Reviewed and deleted unused resources | 26/04/2026 | 26/04/2026 | |

---

### Week 1 Outcomes

* Completed the theoretical modules:

  * Module 01-01 → Became familiar with the Cloud Computing model
  * Module 01-02 → Identified the benefits of using AWS
  * Module 01-03 → Learned about the journey of migrating systems to the Cloud
  * Module 01-04 → Understood the structure of Regions, Availability Zones, and Edge Locations
  * Module 01-05 → Became familiar with the AWS Console and management tools
  * Module 01-06 → Learned the principles of cost control and the AWS Support process
  * Module 01-07 → Consolidated knowledge through research and practical exercises

---

* Completed the practical labs:

  * Lab01-01: Completed the AWS account registration process, recorded the payment issue, and contacted AWS Support

  * Lab01-02: Improved account security using a Virtual MFA Device

  * Lab01-03: Organized access permissions using an Admin Group and IAM User

  * Lab01-04: Completed the verification steps required to restore access to the AWS account

  * Lab07:

    * Created a Cost Budget
    * Monitored the budget based on resource usage
    * Studied Reserved Instance Budgets
    * Studied Savings Plans Budgets
    * Reviewed and deleted experimental Budget configurations

  * Lab09:

    * Compared the available AWS Support plans
    * Learned the use cases for different types of Support Requests
    * Practiced managing and monitoring the progress of a Support Case

---

* Completed all AWS Credit Tasks (5/5):

  * Launch an instance using EC2 → Completed
  * Create an Aurora or RDS database → Completed
  * Set up a cost budget using AWS Budgets → Completed
  * Create a web app using AWS Lambda → Completed
  * Use a foundation model in Amazon Bedrock Playground → Completed

* Results:

  * **Completed all requirements of the AWS Credit Program**
  * **Received 100 USD in AWS Credits for learning and practical exercises**

---

#### 🔹 Amazon RDS Practice — Task Completed

* Successfully deployed a MySQL Database using Amazon RDS.

* Observed:

  * The configuration differences between `t3.micro` and `t3.small`
  * The status transitions during Database creation
  * The backup process performed before the Database changed to the `Available` state

* Key lessons:

  * Amazon RDS may continue generating costs even when no users are accessing the Database
  * Retaining backups after deleting a Database may generate additional costs
  * The retained automated backups option should be reviewed carefully before confirming Database deletion

* Completed the following actions:

  * Deleted the RDS Instance after completing the task
  * Checked the list of remaining backups
  * Deleted Retained Automated Backups that were no longer required

---

#### 🔹 Billing and Cost Awareness

* Monitored cost changes while creating and using AWS resources.

* Identified services and resources that could generate costs:

  * Running EC2 Instances
  * RDS Databases and storage capacity
  * Snapshots or backups that had not been deleted

* Configured alert thresholds to proactively control the budget.

* Key lessons:

  * Users should not rely entirely on the Free Tier label
  * The free usage conditions of each service and resource type should be reviewed carefully
  * The Billing Dashboard should be checked regularly to identify unexpected costs

---

#### 🔹 Security and Access Management

* Configured a second authentication layer using the Authy application.
* Limited the use of the Root Account for daily operations.
* Created an IAM User to perform lab activities with assigned permissions.
* Understood the roles of Users, Groups, and Policies in access management.

---

#### 🔹 Experience Working with AWS Support

* Proactively created a Support Case when the account encountered an issue.
* Prepared the required information and verification documents.
* Monitored responses through email and the AWS Support Center.

* Key lessons:

  * Each Case should clearly describe the problem and provide sufficient evidence
  * The account recovery process may require several verification steps
  * The Case ID should be saved for easier tracking and communication

---

#### 🔹 Skills and Mindset Developed

* Developed troubleshooting skills:

  * Investigated the causes of account restrictions
  * Resolved insufficient permission issues
  * Identified services generating costs
  * Monitored the operational status of AWS resources

* Developed practical Cloud habits:

  * Check permissions before performing operations
  * Monitor resources after deployment
  * Delete Instances, Databases, and Backups when they are no longer required
  * Use AWS Budgets and Billing Alerts to prevent overspending

* Recognized that:

  * An effective Cloud system requires a balance between technical design, security, cost, and operational capability

---
