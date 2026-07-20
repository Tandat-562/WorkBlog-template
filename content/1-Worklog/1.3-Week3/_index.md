
---
title: "Week 3 Worklog"
date: 2026-05-10
weight: 1
chapter: false
pre: " <b> 1.3. </b> "

---

## Week 3 Objectives

* Continue studying the Multi-VPC and Hybrid Connectivity sections of Module 02.
* Administer EC2 Instances in Private Subnets without opening direct access ports to the Internet.
* Study and practice AWS Systems Manager Session Manager.
* Use Interface VPC Endpoints to access AWS services through private networking.
* Connect multiple VPCs using VPC Peering and AWS Transit Gateway.
* Study the roles of Site-to-Site VPN, AWS Direct Connect, and Load Balancers.
* Build a Hybrid DNS model using Route 53 Resolver.
* Control access using IAM Roles, Security Groups, and Network ACLs.
* Complete a troubleshooting process based on IAM, DNS, routing, firewalls, and service agents.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Continued studying the Multi-VPC section of Module 02-02 <br> - Designed a network containing Public and Private Subnets <br> - Created a Linux EC2 Instance for administration and a Windows EC2 Instance as an internal server <br> - Checked Public IPs, Private IPs, and Network Interfaces | 05/04/2026 | 05/04/2026 | https://000058.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 2 | - Created an IAM Role that allowed EC2 to use Systems Manager <br> - Checked the SSM Agent <br> - Configured Security Groups according to the Least Privilege principle <br> - Connected to EC2 using Session Manager instead of direct SSH access | 05/05/2026 | 05/05/2026 | https://000058.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 3 | - Created Interface Endpoints for SSM, SSMMessages, and EC2Messages <br> - Connected to a Private Windows EC2 Instance without a Public IP <br> - Stored Session Manager history in Amazon S3 <br> - Practiced RDP Port Forwarding | 05/06/2026 | 05/06/2026 | https://000058.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 4 | - Created another independent VPC <br> - Established VPC Peering between the two VPCs <br> - Updated Route Tables and Security Groups on both sides <br> - Tested connectivity using Private IP addresses | 05/07/2026 | 05/07/2026 | https://000019.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 5 | - Enabled DNS Resolution for the VPC Peering Connection <br> - Tested Private DNS Hostnames between the two VPCs <br> - Modified Network ACLs to evaluate their impact on traffic <br> - Compared Security Groups with Network ACLs | 05/08/2026 | 05/08/2026 | https://000019.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 6 | - Deployed a Transit Gateway using a hub-and-spoke model <br> - Created Attachments for multiple VPCs <br> - Configured Association and Propagation <br> - Studied AWS Direct Connect and Hybrid Connectivity models | 05/09/2026 | 05/09/2026 | https://000020.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |
| 7 | - Created a Microsoft Active Directory environment <br> - Deployed Route 53 Resolver Inbound and Outbound Endpoints <br> - Created a Resolver Rule for the internal Domain <br> - Studied the role of Load Balancers in traffic distribution <br> - Summarized Module 02 | 05/10/2026 | 05/10/2026 | https://000010.awsstudygroup.com/vi/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |

---

## Week 3 Outcomes

### 1. Completed the Next Part of Module 02

Module 02 was continued during Week 3 as follows:

| Content | Study Scope |
| --- | --- |
| Module 02-02 – Part 2 | VPC Endpoints, VPC Peering, Multi-VPC Networking, and Transit Gateway |
| Module 02-03 – Part 2 | Hybrid Connectivity, Direct Connect, Load Balancing, and DNS Integration |

The practical exercises focused on managing private resources, connecting multiple VPCs, and building DNS communication between different environments.

---

### 2. Managing EC2 Without a Public IP

* Deployed EC2 Instances in Private Subnets.
* Did not assign Public IPs to internal servers.
* Did not expose SSH or RDP directly to the Internet.
* Used AWS Systems Manager to administer the resources.
* Controlled access permissions using IAM.

The following components affected the Managed Node status:

* SSM Agent.
* IAM Instance Profile.
* Connectivity to Systems Manager.
* DNS Resolution.
* VPC Endpoints or NAT Gateways.
* Endpoint Security Groups.

Understood that an EC2 Instance being in the `Running` state does not mean that Session Manager is ready to establish a connection.

---

### 3. Accessing Servers with Session Manager

Session Manager was used as an alternative to direct SSH or RDP access in some situations.

Benefits:

* Administration ports do not need to be exposed to the Internet.
* SSH Keys do not need to be distributed to multiple users.
* Access permissions are managed through IAM.
* Session history can be recorded.
* Servers in Private Subnets can be administered.
* The risk of attacks against SSH and RDP ports is reduced.

Distinctions:

* EC2 permissions do not automatically allow a user to start a Session.
* The user requires appropriate Systems Manager permissions.
* The EC2 Instance also requires an IAM Role to register with Systems Manager.

---

### 4. Private Connectivity Using Interface VPC Endpoints

The following Endpoints were created:

```text
com.amazonaws.<region>.ssm
com.amazonaws.<region>.ssmmessages
com.amazonaws.<region>.ec2messages
```

Connection flow:

```text
Private EC2
    ↓
Private DNS
    ↓
Interface VPC Endpoint
    ↓
AWS Systems Manager
```

Benefits:

* EC2 can call Systems Manager through Private IP addresses.
* Public IP addresses are not required.
* Dependence on a NAT Gateway can be reduced for supported traffic.
* Traffic does not need to pass through the Public Internet.

Requirements:

* Endpoints must be placed in appropriate Subnets.
* Security Groups must allow TCP 443.
* DNS Support and DNS Hostnames must be enabled for the VPC.
* Private DNS must be configured correctly.
* The IAM Role must provide the required permissions.

---

### 5. Access Control Using IAM Roles

Completed the following tasks:

* Created an IAM Role for EC2.
* Attached a Managed Policy for Systems Manager.
* Assigned the Role through an Instance Profile.
* Checked the status after changing the Role.
* Identified errors that occurred when the EC2 Instance lacked permission to register as a Managed Node.

Benefits of Temporary Credentials:

* Access Keys are not stored on EC2.
* Credentials are refreshed automatically.
* Permissions can be changed or revoked through the Role.
* The risk of credential exposure is reduced.
* The Least Privilege principle can be applied.

---

### 6. Recording Administration Session Logs

* Created an S3 Bucket for storing Session Manager logs.
* Configured Session Manager Preferences.
* Checked the EC2 Role's permission to write Objects.
* Checked the Bucket Policy.
* Verified the data after the Session ended.

Session Logging supports:

* Incident investigation.
* Administration activity monitoring.
* Compliance checks.
* Identifying users who accessed a server.
* Storing evidence for Audits.

Possible reasons why logs did not appear:

* The IAM Role lacked permission.
* The Bucket Policy blocked access.
* Session Preferences were incorrect.
* The Bucket used encryption settings that had not been granted permission.
* The Session ended before all data was written.

---

### 7. Port Forwarding to a Windows EC2 Instance

Session Manager was used to create a Tunnel to a Windows EC2 Instance:

```bash
aws ssm start-session \
--target <instance-id> \
--document-name AWS-StartPortForwardingSession \
--parameters portNumber="3389",localPortNumber="9999"
```

Remote Desktop was connected through:

```text
localhost:9999
```

Results:

* The Windows EC2 Instance did not require a Public IP.
* Port 3389 did not need to be opened to the entire Internet.
* Administration traffic passed through Session Manager.
* Permission to create the Tunnel could be restricted through an IAM Policy.

---

### 8. Connecting Two VPCs Using VPC Peering

Completed the following tasks:

* Created a VPC Peering Connection.
* Accepted the connection from the destination VPC.
* Updated Route Tables on both sides.
* Configured Security Groups.
* Tested connectivity using Private IP addresses.
* Enabled DNS Resolution through the Peering Connection.

Connection flow:

```text
EC2 in VPC A
     ↓
Route Table A
     ↓
VPC Peering Connection
     ↓
Route Table B
     ↓
EC2 in VPC B
```

Limitations of VPC Peering:

* Transitive Routing is not supported.
* The CIDR ranges of the two VPCs must not overlap.
* Each connection must be managed separately.
* The number of Routes and Peering Connections increases rapidly as the number of VPCs grows.

VPC Peering is suitable for a small number of VPCs with simple direct connectivity requirements.

---

### 9. DNS Resolution Through VPC Peering

* Enabled DNS Resolution for the Peering Connection.
* Tested Private DNS Hostnames from another VPC.
* Checked DNS Support and DNS Hostnames.
* Distinguished DNS errors from routing or firewall errors.

Possible situations:

* IP connectivity works, but the Hostname cannot be resolved.
* DNS Resolution works, but the Security Group blocks the traffic.
* Routes exist, but DNS Hostnames have not been enabled.
* The Peering Connection is Active, but bidirectional Routes have not been configured.

Understood that DNS and routing must be tested independently.

---

### 10. Security Groups and Network ACLs in Multi-VPC Environments

Traffic was tested at two levels:

* Security Groups attached to ENIs.
* Network ACLs attached to Subnets.

The following traffic types were tested:

* TCP 443 for Interface Endpoints.
* ICMP.
* RDP.
* SSH.
* DNS over TCP/UDP 53.
* Ephemeral Ports for response traffic.

Key lessons:

* Security Groups are Stateful.
* Network ACLs are Stateless.
* NACLs must allow both outbound and return traffic.
* An incorrect NACL Rule can cause connectivity to fail even when the Security Group allows the traffic.

---

### 11. Centralized Connectivity Using Transit Gateway

Transit Gateway was deployed using the following model:

```text
              VPC A
                |
VPC B ─── Transit Gateway ─── VPC C
                |
              VPC D
```

Completed the following tasks:

* Created a Transit Gateway.
* Created Attachments for the VPCs.
* Updated VPC Route Tables.
* Created a Transit Gateway Route Table.
* Configured Association.
* Configured Propagation.
* Tested traffic between multiple VPCs.

Benefits:

* Centralized connectivity management.
* Support for Transitive Routing.
* Reduced number of pair-to-pair connections.
* Suitable for multiple VPCs and multiple AWS Accounts.
* Easier to scale than Full-Mesh Peering.

Points to consider:

* Attachment and data processing costs apply.
* Multiple layers of Route Tables must be checked.
* Association and Propagation must be designed according to network isolation requirements.

---

### 12. Association and Propagation

#### Association

Determines which Transit Gateway Route Table is used to process incoming traffic from an Attachment.

#### Propagation

Allows the Routes of an Attachment to be advertised automatically to a Transit Gateway Route Table.

Three routing layers must be checked:

```text
Source VPC Route Table
          ↓
Transit Gateway Route Table
          ↓
Destination VPC Route Table
```

An Attachment being in the `Available` state does not guarantee communication between two VPCs when Routes or firewall rules are incorrect.

---

### 13. AWS Direct Connect Overview

Studied the role of AWS Direct Connect in Hybrid Cloud architectures:

* Provides a private network connection from an enterprise environment to AWS.
* Primary traffic does not pass through the Public Internet.
* Can provide higher bandwidth and more stable connectivity than an Internet-based VPN.
* Commonly used for systems that transfer large amounts of data or require stable connectivity.

General comparison:

| Site-to-Site VPN | AWS Direct Connect |
| --- | --- |
| Uses an Internet connection | Uses a private network connection |
| Faster to deploy | Requires a longer setup process |
| Lower initial cost | Includes physical connection and Port costs |
| Suitable as a backup connection | Suitable for stable, large-scale traffic |
| Provides IPsec encryption | Does not automatically provide encryption like IPsec |

In many architectures, Direct Connect can be combined with a VPN to improve security and redundancy.

---

### 14. Load Balancer Overview

Studied the role of Elastic Load Balancing:

* Distributes traffic across multiple Targets.
* Checks Target status using Health Checks.
* Improves scalability and availability.
* Prevents users from connecting directly to individual EC2 Instances.

Basic distinctions:

| Load Balancer | Use Case |
| --- | --- |
| Application Load Balancer | HTTP/HTTPS, Host-Based Routing, and Path-Based Routing |
| Network Load Balancer | TCP/UDP, high performance, and low latency |
| Gateway Load Balancer | Deploying virtual networking or security appliances |

A Load Balancer is an important component when deploying applications across multiple Availability Zones.

---

### 15. Building Hybrid DNS with Route 53 Resolver

Completed the following deployments:

* Inbound Resolver Endpoint.
* Outbound Resolver Endpoint.
* Resolver Rule.
* Target DNS Server.
* Rule Association with a VPC.

Query flow:

```text
On-Premises DNS
       ↓
Inbound Resolver Endpoint
       ↓
Amazon Route 53 Resolver
       ↓
Private Hosted Zone
```

And:

```text
AWS Workload
      ↓
Outbound Resolver Endpoint
      ↓
Resolver Rule
      ↓
On-Premises DNS Server
```

The following requirements were checked:

* Security Groups allow TCP/UDP 53.
* Routes exist to the destination DNS Server.
* The Resolver Rule uses the correct Domain.
* Endpoints are deployed in appropriate Subnets.
* The VPC is associated with the Resolver Rule.

---

### 16. Microsoft Active Directory and DNS

* Created a Microsoft Active Directory environment.
* Checked the Domain Controller and DNS Server.
* Tested the resolution of internal Domain records.
* Tested Remote Desktop connectivity.
* Analyzed the DNS flow between AWS and the Hybrid environment.

Understood that:

* Active Directory depends heavily on DNS.
* Domain Join can fail when DNS is configured incorrectly.
* Successful Ping does not prove that Active Directory is functioning correctly.
* DNS Records and related service ports must also be checked.
* The DNS Server used by a Client must be able to resolve the internal Domain.

---

### 17. Comparing Connectivity Solutions

| Solution | Suitable Use Case | Important Considerations |
| --- | --- | --- |
| VPC Peering | Direct connection between a small number of VPCs | Does not support Transitive Routing |
| Transit Gateway | Centralized connectivity between multiple VPCs | Has additional costs and multiple routing layers |
| Interface VPC Endpoint | Private access to AWS Services | Requires correct DNS, Endpoint, and Security Group configuration |
| Session Manager | EC2 administration without public ports | Depends on IAM Roles, Agents, and network connectivity |
| Site-to-Site VPN | Connects AWS to an external network through the Internet | Requires IPsec Tunnel and routing management |
| AWS Direct Connect | Stable Hybrid connectivity with high bandwidth | Requires a physical connection and setup time |
| Route 53 Resolver | Connects DNS between AWS and external environments | Depends on correct routing and DNS Forwarding |
| Load Balancer | Distributes traffic across multiple Targets | Requires Health Checks and a Multi-AZ design |

---

## Practical Issues Resolved

### 1. EC2 Did Not Appear in Managed Nodes

The following components were checked:

* SSM Agent.
* IAM Role.
* Instance Profile.
* DNS Resolution.
* Interface Endpoint.
* Security Group TCP 443.
* Connectivity to Systems Manager.

Verification commands:

```bash
sudo systemctl status amazon-ssm-agent
sudo systemctl restart amazon-ssm-agent
```

---

### 2. Private EC2 Could Not Connect to Systems Manager

Possible causes:

* Missing Endpoints.
* Private DNS was not enabled.
* The Endpoint Security Group blocked HTTPS.
* The Subnet did not have a NAT Gateway.
* The IAM Role lacked permissions.
* The SSM Agent was not running.

---

### 3. Port Forwarding Worked but RDP Failed

The following components were checked:

* The Windows EC2 Instance was running.
* The RDP Service was active.
* The destination Port was `3389`.
* The Local Port was not being used by another application.
* Security Groups between the Managed Instance and Windows EC2 Instance.
* Routes between the two Subnets or VPCs.
* Windows Firewall.

---

### 4. Session Logs Did Not Appear in Amazon S3

The following possible causes were reviewed:

* The IAM Role lacked `s3:PutObject`.
* The Bucket Policy did not allow access.
* Session Manager Preferences were incorrect.
* The KMS Key Policy did not allow encryption.
* The Session had not completely ended.

---

### 5. VPC Peering Was Active but Connectivity Failed

Resolution steps:

* Verified that CIDR ranges did not overlap.
* Added Routes on both sides.
* Checked Security Groups.
* Checked Network ACLs.
* Enabled DNS Resolution when Hostnames were used.
* Confirmed the correct Private IP addresses.

---

### 6. Transit Gateway Attachment Was Available but Traffic Failed

The following components were checked:

* Source VPC Route Table.
* Transit Gateway Association.
* Transit Gateway Propagation.
* Transit Gateway Route Table.
* Destination VPC Route Table.
* Security Groups.
* Network ACLs.
* Return Routes.

---

### 7. Resolver Endpoint Was Active but DNS Queries Timed Out

The following possible causes were checked:

* TCP/UDP 53 was blocked.
* The Resolver Rule used the wrong Domain.
* The Target DNS Server IP was incorrect.
* A Route to the DNS Server was missing.
* The Rule had not been associated with the VPC.
* The DNS Server did not contain the requested record.

---

## Troubleshooting Process Developed

When a connectivity issue occurred, the following order was used:

1. Identify the Source and Destination.
2. Check Private IP addresses, ENIs, and Subnets.
3. Check the Source Route Table.
4. Check VPC Peering or Transit Gateway configuration.
5. Check the Destination Route Table.
6. Check Security Groups on both sides.
7. Check Network ACLs.
8. Check DNS when Hostnames are used.
9. Check IAM Roles when an AWS Service is involved.
10. Check Agents or Services running on EC2.
11. Check Logs and Flow Logs when the cause remains unclear.

This process helps prevent multiple configurations from being changed at the same time and makes it easier to identify the actual cause of an issue.

---

## Skills Developed

* Managing EC2 using Session Manager.
* Using IAM Roles for EC2.
* Creating Interface VPC Endpoints.
* Storing Session Logs in Amazon S3.
* Creating Port Forwarding sessions to Windows EC2.
* Connecting VPCs using VPC Peering.
* Designing Multi-VPC networking using Transit Gateway.
* Configuring Association and Propagation.
* Building Route 53 Resolver Endpoints.
* Analyzing the roles of Direct Connect and Load Balancers.
* Troubleshooting IAM, DNS, routing, and firewall issues.

---

## Self-Evaluation

* Developed a stronger understanding of:

  * Systems Manager Session Manager.
  * Interface VPC Endpoints.
  * VPC Peering.
  * Transit Gateway.
  * Hybrid Connectivity.
  * AWS Direct Connect.
  * Elastic Load Balancing.
  * Route 53 Resolver.
  * Microsoft Active Directory and DNS.

* Able to:

  * Administer EC2 Instances without Public IP addresses.
  * Connect to Windows EC2 through Port Forwarding.
  * Connect two VPCs using Peering.
  * Design centralized connectivity using Transit Gateway.
  * Analyze DNS flows in a Hybrid Cloud environment.
  * Troubleshoot issues using IAM, DNS, routing, and firewall information.

* Areas for further improvement:

  * Develop a deeper understanding of Endpoint Policies.
  * Practice reading Transit Gateway Route Tables.
  * Study Active Directory service ports in more detail.
  * Practice Load Balancers with Auto Scaling.
  * Study the practical deployment process of Direct Connect.
  * Optimize the costs of Interface Endpoints and Transit Gateway.

---

## Next Steps

* Study the following topics:

  * BGP Routing.
  * Direct Connect Gateway.
  * AWS Network Firewall.
  * VPC Flow Logs.
  * AWS Cloud WAN.
  * Gateway Load Balancer.

* Continue practicing:

  * Collecting VPC Flow Logs.
  * Building a Centralized Inspection VPC.
  * Connecting Transit Gateways across multiple Regions.
  * Separating Development, Testing, and Production environments.
  * Deploying an Application Load Balancer.
  * Configuring highly available DNS Forwarding.
  * Building a Hybrid Cloud architecture that combines VPN, Direct Connect, and Route 53 Resolver.

---

