
---
title: "Week 8 Worklog"
date: 2026-06-14
weight: 1
chapter: false
pre: " <b> 1.8. </b> "

---

## Week 8 Objectives

* Complete Module 05 about security, identity management, and access control on AWS.
* Understand the AWS Shared Responsibility Model and the responsibilities of AWS compared with those of customers.
* Study the architecture of AWS Identity and Access Management.
* Distinguish between IAM Users, IAM Groups, IAM Roles, IAM Policies, and Permission Boundaries.
* Study the process of authenticating and authorizing application users with Amazon Cognito.
* Study the multi-account governance model using AWS Organizations.
* Learn about centralized sign-in using AWS IAM Identity Center.
* Understand how AWS Key Management Service manages encryption keys and protects data.
* Study AWS Security Hub and the process of centralizing security findings.
* Practice access control using IAM Conditions, Resource Tags, and Temporary Credentials.
* Apply the Least Privilege principle when granting permissions.
* Improve troubleshooting skills related to IAM, Roles, Policies, encryption, and security governance.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Studied Module 05-01 about the AWS Shared Responsibility Model <br> - Distinguished between the security responsibilities of AWS and customers <br> - Learned how responsibilities change according to the type of service <br> - Reviewed Root User security and MFA | 08/06/2026 | 08/06/2026 | https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=150 |
| 2 | - Studied Module 05-02 about AWS Identity and Access Management <br> - Learned about IAM Users, Groups, Roles, and Policies <br> - Analyzed the Authentication and Authorization process <br> - Practiced managing IAM Users, Groups, and Roles | 09/06/2026 | 09/06/2026 | https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151, https://000002.awsstudygroup.com/vi/ |
| 3 | - Studied Module 05-03 about Amazon Cognito <br> - Distinguished between User Pools and Identity Pools <br> - Learned about user registration, sign-in, and Token issuance for applications <br> - Reviewed IAM Roles used by applications to access AWS | 10/06/2026 | 10/06/2026 | https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152, https://000048.awsstudygroup.com/vi/ |
| 4 | - Studied Module 05-04 about AWS Organizations <br> - Learned about Management Accounts, Member Accounts, and Organizational Units <br> - Analyzed Service Control Policies <br> - Practiced Assume Role, Trust Policies, and IAM Conditions | 11/06/2026 | 11/06/2026 | https://www.youtube.com/watch?v=5oQY8Rogz9Y&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153, https://000044.awsstudygroup.com/vi/ |
| 5 | - Studied Module 05-05 about AWS IAM Identity Center <br> - Enabled IAM Identity Center <br> - Created Users, Groups, and Permission Sets <br> - Assigned access to AWS Accounts <br> - Configured AWS CLI sign-in using SSO | 12/06/2026 | 12/06/2026 | https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=154, https://000012.awsstudygroup.com/vi/ |
| 6 | - Studied Module 05-06 about AWS Key Management Service <br> - Learned about KMS Keys, Key Policies, and Data Keys <br> - Distinguished between symmetric and asymmetric encryption <br> - Practiced IAM Policy Conditions and EC2 access control using Resource Tags | 13/06/2026 | 13/06/2026 | https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155, https://000028.awsstudygroup.com/vi/ |
| 7 | - Studied the final sections of Module 05 <br> - Learned about AWS Security Hub and the Security Findings management process <br> - Summarized knowledge about Identity, Encryption, Governance, and Security Monitoring <br> - Reviewed IAM, Permission Set, KMS, and Security Hub issues | 14/06/2026 | 14/06/2026 | https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156, https://www.youtube.com/watch?v=0SdpD2GPYz4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157 |

---

## Week 8 Outcomes

### 1. Completed Module 05

The following main topics were studied:

| Module | Content |
| --- | --- |
| Module 05-01 | AWS Shared Responsibility Model |
| Module 05-02 | AWS Identity and Access Management |
| Module 05-03 | Amazon Cognito |
| Module 05-04 | AWS Organizations |
| Module 05-05 | AWS IAM Identity Center |
| Module 05-06 | AWS Key Management Service |
| Module 05-07 | AWS Security Hub and Security Findings Management |
| Module 05-08 | Overview of AWS Security, Governance, and Monitoring |

After completing Module 05, I gained a clearer understanding of how AWS manages identities, permissions, encryption, multi-account governance, and the security posture of systems.

---

### 2. AWS Shared Responsibility Model

The AWS Shared Responsibility Model divides security responsibilities into two groups:

```text
AWS
├── Security of the Cloud
│   ├── Data Centers
│   ├── Hardware
│   ├── Network Infrastructure
│   ├── Virtualization Layer
│   └── Service Infrastructure
│
└── Customer
    └── Security in the Cloud
        ├── Data
        ├── IAM
        ├── Operating Systems
        ├── Applications
        ├── Network Configuration
        └── Encryption and Key Management
```

Understood that:

* AWS is responsible for protecting the infrastructure that operates AWS services.
* Customers are responsible for their data, accounts, access permissions, and configurations.
* The level of customer responsibility changes according to the type of service.
* With Amazon EC2, customers manage the operating system, applications, and Security Groups.
* With managed services such as Amazon S3 or DynamoDB, AWS manages more of the underlying infrastructure.
* An AWS-managed service does not mean that customers have no remaining security responsibilities.

---

### 3. Protecting the AWS Root User

The Root User has the highest level of access within an AWS Account.

Security principles:

* Do not use the Root User for daily work.
* Enable MFA for the Root User.
* Do not create an Access Key for the Root User unless it is absolutely necessary.
* Use a securely controlled email address.
* Protect billing and account recovery information.
* Use the Root User only for tasks that specifically require it.
* Monitor unusual sign-in activity.

Daily operations should be performed using IAM Users, IAM Roles, or IAM Identity Center.

---

### 4. AWS IAM Architecture

AWS IAM is used to manage access to AWS services and resources.

Main components:

```text
Identity
├── IAM User
├── IAM Group
└── IAM Role

Permission
├── Identity-Based Policy
├── Resource-Based Policy
├── Permission Boundary
├── Service Control Policy
└── Session Policy
```

#### IAM User

* Represents a specific user or use case.
* Can sign in to the AWS Console.
* Can use an Access Key for AWS CLI or API access.
* Has no permissions by default when first created.

#### IAM Group

* Groups multiple IAM Users.
* Helps manage permissions according to job roles.
* Policies attached to the Group apply to its members.

#### IAM Role

* Does not have long-term credentials.
* Is used through Assume Role.
* AWS STS issues Temporary Credentials.
* Can be used by Users, AWS Services, or applications.

---

### 5. IAM Policy

An IAM Policy is a JSON document that defines access permissions.

Basic structure:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances"
      ],
      "Resource": "*"
    }
  ]
}
```

Main elements:

* `Effect`: Allow or Deny.
* `Action`: The operation that is allowed or denied.
* `Resource`: The resource to which the Policy applies.
* `Condition`: Additional conditions.
* `Principal`: The entity to which a Resource-Based Policy applies.

Important principles:

* By default, all access is denied.
* Access is granted only when an appropriate `Allow` exists.
* An `Explicit Deny` always takes priority over an `Allow`.
* `Action: "*"` and `Resource: "*"` should not be used unless necessary.

---

### 6. IAM Permission Evaluation Process

General process:

```text
User or Application Sends a Request
            ↓
AWS Authenticates the Identity
            ↓
Evaluate Identity-Based Policy
            ↓
Evaluate Resource-Based Policy
            ↓
Evaluate Permission Boundary
            ↓
Evaluate Service Control Policy
            ↓
Evaluate Session Policy
            ↓
Allow or Deny
```

Effective Permissions are the result of multiple Policy layers working together.

An Identity with an Allow Policy may still be unable to perform an action when:

* The Permission Boundary does not allow it.
* The Service Control Policy does not allow it.
* The Resource Policy contains an Explicit Deny.
* The KMS Key Policy does not allow it.
* The Trust Policy does not allow Assume Role.
* A Policy Condition is not satisfied.

---

### 7. IAM Roles and Temporary Credentials

Assume Role process:

```text
IAM User or AWS Service
          ↓
Calls AWS STS AssumeRole
          ↓
Trust Policy Is Evaluated
          ↓
Temporary Credentials Are Issued
          ↓
Permissions of the IAM Role Are Used
          ↓
Credentials Expire Automatically
```

Temporary Credentials normally include:

* Access Key ID.
* Secret Access Key.
* Session Token.
* Expiration Time.

Benefits:

* Long-term credentials do not need to be stored.
* Credentials expire automatically.
* The risk of Access Key exposure is reduced.
* Session duration and conditions can be restricted.
* Suitable for EC2, Lambda, and applications running on AWS.

---

### 8. IAM Trust Policy

A Trust Policy defines which entity is allowed to assume a Role.

Example:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::<account-id>:user/example-user"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

For Assume Role to succeed, the following must be checked:

* The User has `sts:AssumeRole` permission.
* The Role Trust Policy allows the corresponding User or Account.
* Policy Conditions are satisfied.
* The Service Control Policy does not block the action.
* The Permission Boundary does not restrict the required permission.

---

### 9. IAM Policy Conditions

IAM Conditions allow more detailed access control.

Conditions can be based on:

* IP address.
* Time.
* Region.
* Resource Tags.
* Request Tags.
* Principal Tags.
* MFA.
* VPC Endpoints.
* AWS Accounts.
* Organization IDs.

Example of a Region restriction:

```json
"Condition": {
  "StringEquals": {
    "aws:RequestedRegion": "ap-southeast-1"
  }
}
```

Example requiring MFA:

```json
"Condition": {
  "Bool": {
    "aws:MultiFactorAuthPresent": "true"
  }
}
```

---

### 10. Access Control Using Resource Tags

Practiced granting EC2 management permissions based on Tags.

Example:

```text
Team = Alpha
Environment = Development
Owner = FCJ-Team
```

Access control flow:

```text
User Sends an EC2 Management Request
          ↓
IAM Checks the Resource Tag
          ↓
Does the Tag Match the Policy Condition?
          ↓
Yes → Allow
No  → Deny
```

The following Policies were studied and tested:

* `ec2-list-read`
* `ec2-create-tags`
* `ec2-create-tags-existing`
* `ec2-run-instances`
* `ec2-manage-instances`

Results:

* Restricted Users to managing only EC2 Instances with matching Tags.
* Required Tags when creating Instances.
* Restricted actions by Region.
* Prevented Users from managing resources owned by other teams.
* Applied Attribute-Based Access Control.

---

### 11. IAM Permission Boundary

A Permission Boundary defines the maximum level of permission that an IAM User or IAM Role can receive.

Effective Permissions can be represented as follows:

```text
IAM Identity Policy
          ∩
Permission Boundary
          =
Effective Permission
```

Example:

* The Identity Policy allows full EC2 management.
* The Permission Boundary allows operations only in `ap-southeast-1`.
* The User can manage EC2 only in `ap-southeast-1`.

A Permission Boundary does not grant permissions by itself. It only limits permissions granted by Identity-Based Policies.

Use cases:

* Allow Developers to create Roles without exceeding defined limits.
* Prevent Privilege Escalation.
* Restrict administrative access by Region or Service.
* Delegate permissions in environments with multiple development teams.

---

### 12. Amazon Cognito

Amazon Cognito provides identity management capabilities for application users.

The two main components are:

#### Cognito User Pool

* Manages user registration and sign-in.
* Stores user information.
* Supports email or phone number verification.
* Supports MFA.
* Issues JWT Tokens.
* Can integrate with Social Identity Providers and SAML.

#### Cognito Identity Pool

* Issues Temporary AWS Credentials.
* Maps users to IAM Roles.
* Allows applications to access AWS resources.
* Supports both authenticated and unauthenticated users.

Operation flow:

```text
User Signs In
        ↓
Cognito User Pool
        ↓
Receives JWT Token
        ↓
Cognito Identity Pool
        ↓
Assumes IAM Role
        ↓
Receives Temporary AWS Credentials
        ↓
Accesses AWS Services
```

---

### 13. AWS Organizations

AWS Organizations supports centralized management of multiple AWS Accounts.

Structure:

```text
Organization Root
├── Management Account
├── Security OU
│   ├── Log Archive Account
│   └── Security Tooling Account
├── Production OU
│   └── Production Account
└── Development OU
    ├── Development Account
    └── Testing Account
```

Main components:

* Management Account.
* Member Account.
* Organization Root.
* Organizational Unit.
* Service Control Policy.
* Consolidated Billing.

Benefits:

* Separates workloads by Account.
* Provides centralized management.
* Applies Policies by OU.
* Consolidates Billing.
* Limits the scope of impact when an incident occurs.
* Supports Landing Zone design.

---

### 14. Service Control Policy

A Service Control Policy defines the maximum available permissions for an Account or OU in AWS Organizations.

An SCP:

* Does not directly grant permissions.
* Only limits which permissions can be used.
* Can be applied to an Account or OU.
* Does not replace IAM Policies.
* Can prevent the use of certain services or Regions.

Example:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "aws:RequestedRegion": [
            "ap-southeast-1"
          ]
        }
      }
    }
  ]
}
```

This Policy can be used to restrict activity outside the permitted Region.

---

### 15. AWS IAM Identity Center

IAM Identity Center supports centralized sign-in management for multiple AWS Accounts and applications.

Architecture:

```text
Identity Source
      ↓
IAM Identity Center
      ↓
Users and Groups
      ↓
Permission Sets
      ↓
AWS Account Assignments
      ↓
AWS Access Portal or AWS CLI
```

Completed the following tasks:

* Enabled AWS Organizations.
* Enabled IAM Identity Center.
* Created a User.
* Created a Group.
* Created a Permission Set.
* Assigned Users and Groups to AWS Accounts.
* Tested Administrator and Read-Only permissions.
* Configured AWS CLI to use SSO.

Created objects:

* Administrators Group.
* ReadOnly Group.
* Admin User.
* ReadOnly User.

---

### 16. Permission Sets

A Permission Set is a permission template used by IAM Identity Center to grant access to AWS Accounts.

A Permission Set can include:

* AWS Managed Policies.
* Customer Managed Policies.
* Inline Policies.
* Permission Boundaries.
* Session Duration.
* Relay State.

When a Permission Set is assigned to an Account, IAM Identity Center creates a corresponding IAM Role in the destination Account.

Benefits:

* Centralized permission management.
* No need to create separate IAM Users in every Account.
* Easier permission revocation.
* Supports multiple Accounts.
* Uses time-limited Credentials.
* Reduces the use of long-term Access Keys.

---

### 17. AWS CLI with IAM Identity Center

Configuration process:

```bash
aws configure sso
```

The user then provides:

* SSO Start URL.
* SSO Region.
* AWS Account.
* Permission Set or Role.
* CLI Profile Name.

Sign-in command:

```bash
aws sso login --profile <profile-name>
```

Identity verification:

```bash
aws sts get-caller-identity --profile <profile-name>
```

Benefits:

* Long-term Access Keys do not need to be stored.
* Uses Session Credentials.
* Supports browser-based sign-in.
* Permissions are managed centrally.
* Supports multiple Accounts and Roles.

---

### 18. AWS Key Management Service

AWS KMS is a managed encryption key service.

Main components:

```text
KMS Key
├── Key Material
├── Key Policy
├── Alias
├── Key ID
└── Key Metadata
```

AWS KMS integrates with many services:

* Amazon S3.
* Amazon EBS.
* Amazon RDS.
* Amazon DynamoDB.
* AWS Lambda.
* AWS Secrets Manager.
* Amazon CloudWatch Logs.
* Amazon SNS.
* Amazon SQS.

---

### 19. Types of KMS Keys

#### AWS Owned Key

* Owned and managed by AWS.
* Used across multiple AWS Accounts.
* Not directly managed by customers.

#### AWS Managed Key

* Created in an Account when an AWS service is used.
* Managed by AWS.
* Has an Alias in the format `aws/<service>`.

#### Customer Managed Key

* Created and managed by the customer.
* Supports editable Key Policies.
* Can be enabled or disabled.
* Supports Key Rotation.
* Supports Aliases.
* Provides detailed permission control.

---

### 20. Envelope Encryption

Envelope Encryption uses a Data Key to encrypt data.

Process:

```text
Application Requests GenerateDataKey
          ↓
AWS KMS Creates a Plaintext Data Key
and an Encrypted Data Key
          ↓
Plaintext Data Key Encrypts the Data
          ↓
Plaintext Data Key Is Removed from Memory
          ↓
Encrypted Data Key Is Stored with the Ciphertext
```

Decryption process:

```text
Encrypted Data Key
        ↓
AWS KMS Decrypt
        ↓
Plaintext Data Key
        ↓
Decrypt the Data
```

Benefits:

* The entire dataset does not need to be sent to AWS KMS.
* Suitable for large amounts of data.
* Reduces the number of direct operations using a KMS Key.
* Separates the data encryption key from the encrypted data.

---

### 21. KMS Key Policy

A KMS Key Policy defines which entities can use and manage a KMS Key.

Common permissions:

* `kms:Encrypt`
* `kms:Decrypt`
* `kms:GenerateDataKey`
* `kms:DescribeKey`
* `kms:CreateGrant`
* `kms:EnableKey`
* `kms:DisableKey`

Successfully using a KMS Key may require:

* An IAM Policy that allows access.
* A Key Policy that allows access.
* A Service Control Policy that does not block access.
* A Permission Boundary that does not block access.
* The correct Region and Key ARN.

---

### 22. AWS Security Hub

AWS Security Hub provides a centralized location for monitoring security posture.

Operation flow:

```text
AWS Security Services
├── Amazon GuardDuty
├── Amazon Inspector
├── Amazon Macie
├── IAM Access Analyzer
└── Partner Solutions
          ↓
     Security Findings
          ↓
    AWS Security Hub
          ↓
Classify and Prioritize Findings
          ↓
Investigate and Remediate
```

Security Hub supports:

* Aggregating Security Findings.
* Standardizing Finding data.
* Evaluating resources against Security Standards.
* Classifying Findings by severity.
* Providing information about affected resources.
* Integrating with EventBridge for automation.
* Tracking remediation status.

---

### 23. Security Standards and Security Findings

Security Hub can evaluate an environment using security standards and control sets.

Each Finding may include:

* Title.
* Description.
* Severity.
* Resource.
* Region.
* AWS Account.
* Compliance Status.
* Remediation Recommendation.
* Workflow Status.

Workflow states:

```text
NEW
  ↓
NOTIFIED
  ↓
RESOLVED
```

Or:

```text
SUPPRESSED
```

Security Hub should not be enabled without also establishing a process for reviewing and resolving Findings.

---

## Practical Issues Resolved

### 1. IAM User Still Received Access Denied After a Policy Was Attached

The following possible causes were checked:

* The Policy had not been attached to the correct User or Group.
* The Policy used the wrong Action.
* The Resource ARN was incorrect.
* An Explicit Deny existed.
* A Permission Boundary restricted access.
* An SCP restricted access.
* A Policy Condition was not satisfied.
* The previous Session had not been refreshed.

---

### 2. Unable to Assume Role

The following components were checked:

* The User had `sts:AssumeRole` permission.
* The Role Trust Policy.
* Principal ARN.
* Role ARN.
* External ID when required.
* IP conditions.
* Time conditions.
* MFA conditions.
* Session Duration.

---

### 3. Resource Tag Policy Did Not Work

The following possible causes were reviewed:

* Incorrect Tag Key.
* Tag values were case-sensitive.
* `aws:ResourceTag` and `aws:RequestTag` were confused.
* The Tag did not exist at the time of evaluation.
* The Action did not support the selected Condition type.
* Related resources such as EBS Volumes had not been tagged.

---

### 4. Permission Set Was Created but the User Could Not Access the Account

The following items were checked:

* The User or Group had been assigned to the correct AWS Account.
* The Permission Set had been provisioned.
* The User was using the correct Access Portal.
* The old Session had not expired.
* The Identity Source had been synchronized.
* The Permission Set was not restricted by an SCP.

---

### 5. AWS CLI SSO Sign-In Failed

The following possible causes were checked:

* Incorrect SSO Start URL.
* Incorrect SSO Region.
* The Profile had not been configured.
* The Token had expired.
* The User had not received an Account Assignment.
* Browser authentication had not been completed.

Resolution commands:

```bash
aws sso logout
aws sso login --profile <profile-name>
```

---

### 6. KMS Access Denied

The following components were checked:

* IAM Policy.
* KMS Key Policy.
* Key ARN.
* Region.
* Key State.
* Grants.
* SCP.
* Permission Boundary.
* The AWS service calling KMS lacked permissions.

---

### 7. Findings Did Not Appear in Security Hub

The following possible causes were reviewed:

* Security Hub had not been enabled in the correct Region.
* The Security Standard had not been enabled.
* The security service integration had not been enabled.
* The Finding had been archived or suppressed.
* No assessment data was available yet.
* IAM permissions were insufficient to view Findings.
* Interface filters were hiding the Findings.

---

## IAM Troubleshooting Process Developed

When an access issue occurred, the following order was used:

1. Identify the Principal sending the Request.
2. Identify the Action and Resource.
3. Check the Identity-Based Policy.
4. Check the Resource-Based Policy.
5. Check the Trust Policy when Assume Role is involved.
6. Check the Permission Boundary.
7. Check the Service Control Policy.
8. Check the Session Policy.
9. Check Policy Conditions.
10. Check the KMS Key Policy when encrypted data is involved.
11. Use CloudTrail or Policy Simulator to support the investigation.

This process helps avoid granting overly broad permissions simply to resolve an `AccessDenied` error quickly.

---

## Skills Developed

* Understanding the AWS Shared Responsibility Model.
* Protecting the AWS Root User.
* Creating and managing IAM Users, Groups, and Roles.
* Writing and analyzing IAM Policies.
* Understanding the permission evaluation process.
* Performing Assume Role.
* Using Temporary Credentials.
* Configuring IAM Policy Conditions.
* Controlling access using Resource Tags.
* Applying Permission Boundaries.
* Understanding Amazon Cognito User Pools and Identity Pools.
* Organizing multiple Accounts using AWS Organizations.
* Understanding Service Control Policies.
* Configuring AWS IAM Identity Center.
* Signing in to AWS CLI using SSO.
* Understanding how AWS KMS manages keys.
* Analyzing KMS Key Policies.
* Monitoring Findings using AWS Security Hub.
* Troubleshooting IAM, KMS, and Permission Set issues.

---

## Self-Evaluation

* Completed all content in Module 05.
* Understood the division of security responsibilities between AWS and customers.
* Able to distinguish between Authentication and Authorization.
* Understood the roles of Users, Groups, Roles, and Policies in AWS IAM.
* Able to analyze the multiple layers affecting Effective Permissions.
* Understood how applications use Amazon Cognito for user authentication.
* Learned how AWS Organizations manages multiple Accounts.
* Able to configure Users, Groups, and Permission Sets in IAM Identity Center.
* Understood key management and Envelope Encryption using AWS KMS.
* Understood the role of Security Hub in aggregating and monitoring Security Findings.
* Improved troubleshooting skills related to access permissions.

Areas for further improvement:

* Practice more with IAM Policy Simulator.
* Study Attribute-Based Access Control in greater depth.
* Practice Amazon Cognito with a real application.
* Create an AWS Organizations environment with multiple Member Accounts.
* Study AWS Control Tower.
* Practice KMS Grants and Key Rotation.
* Integrate Security Hub with EventBridge and SNS.
* Study Amazon GuardDuty, Inspector, and Macie.
* Build an automated remediation process for Security Findings.

---

## Next Steps

* Prepare for the next Module.
* Join group discussions about the AWS project.
* Apply security knowledge to the project architecture:

  * Separate permissions using IAM Roles.
  * Reduce the use of Access Keys.
  * Apply Least Privilege.
  * Protect data using AWS KMS.
  * Monitor Security Findings.
  * Use Resource Tags for permission management.
  * Design separate permissions for individual components.

* Continue studying:

  * Amazon GuardDuty.
  * Amazon Inspector.
  * Amazon Macie.
  * AWS Config.
  * AWS CloudTrail.
  * Amazon CloudWatch.
  * AWS WAF.
  * AWS Shield.
  * AWS Secrets Manager.
  * AWS Systems Manager Parameter Store.

---

