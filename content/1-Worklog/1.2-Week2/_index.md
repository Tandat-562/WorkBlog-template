
---
title: "Week 2 Worklog"
date: 2026-05-03
weight: 1
chapter: false
pre: " <b> 1.2. </b> "

---

## Week 2 Objectives

* Study the first part of Module 02 about Amazon Virtual Private Cloud.
* Understand how to design a private network on AWS using VPCs, Subnets, and CIDR blocks.
* Distinguish between Public Subnets and Private Subnets.
* Learn the roles of Route Tables, Internet Gateways, NAT Gateways, Elastic IPs, and ENIs.
* Study network security mechanisms using Security Groups and Network ACLs.
* Practice building an AWS Site-to-Site VPN connection.
* Use Amazon EC2 and Libreswan to simulate a Customer Gateway.
* Develop troubleshooting skills related to routing, firewalls, and IPsec VPNs.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Completed the AWS Account activation process <br> - Verified the 100 USD AWS Credit <br> - Configured MFA to improve account security <br> - Prepared the environment for networking exercises | 05/01/2026 | 05/01/2026 | https://www.youtube.com/watch?v=2QSXYi6Ofmc&list=PLgT9f4ZU9cncuJ5ACqQxook4yKO1xuZP6&index=10, https://www.youtube.com/watch?v=dCs6UWGMe_A&list=PLgT9f4ZU9cncuJ5ACqQxook4yKO1xuZP6&index=11 |
| 2 | - Studied Module 02-01 about Amazon VPC <br> - Learned about VPCs, Subnets, CIDR blocks, ENIs, and Elastic IPs <br> - Practiced dividing the `10.0.0.0/16` network into `/24` Subnets | 05/02/2026 | 05/02/2026 | https://www.youtube.com/watch?v=O9Ac_vGHquM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=25 |
| 3 | - Created a VPC and Public/Private Subnets <br> - Attached an Internet Gateway to the VPC <br> - Configured the Route Table for the Public Subnet <br> - Launched an EC2 Instance and tested Internet connectivity | 05/02/2026 | 05/02/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=O9Ac_vGHquM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=25 |
| 4 | - Allocated an Elastic IP and created a NAT Gateway <br> - Updated the Route Table for the Private Subnet <br> - Tested outbound connectivity from a Private EC2 Instance <br> - Monitored resources that could generate costs | 05/02/2026 | 05/02/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=O9Ac_vGHquM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=25 |
| 5 | - Studied the VPC Security section of Module 02-02 <br> - Configured Security Groups and Network ACLs <br> - Compared Stateful and Stateless mechanisms <br> - Tested SSH, ICMP, and Ephemeral Port traffic | 05/03/2026 | 05/03/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26 |
| 6 | - Studied the VPN section of Module 02-03 <br> - Used an EC2 Instance as a Customer Gateway <br> - Created a Virtual Private Gateway and VPN Connection <br> - Downloaded the configuration for two VPN Tunnels | 05/03/2026 | 05/03/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |
| 7 | - Installed and configured Libreswan IPsec on EC2 <br> - Checked IKE Phase 1 and IPsec Phase 2 <br> - Resolved issues related to Security Groups, Route Tables, and NAT Traversal <br> - Summarized the first part of Module 02 | 05/03/2026 | 05/03/2026 | https://000003.awsstudygroup.com/vi/6-cleanup/, https://www.youtube.com/watch?v=CXU8D3kyxIc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=27 |

---

## Week 2 Outcomes

### 1. Completed the First Part of Module 02

The Module 02 content studied during Week 2 was divided as follows:

| Content | Study Scope |
| --- | --- |
| Module 02-01 | Amazon VPC, Subnets, CIDR blocks, ENIs, Elastic IPs, Internet Gateways, and NAT Gateways |
| Module 02-02 – Part 1 | VPC Security using Security Groups and Network ACLs |
| Module 02-03 – Part 1 | AWS Site-to-Site VPN, Customer Gateway, and IPsec Tunnels |

Through this part of the module, I developed a foundational understanding of how to organize private networks, provide Internet connectivity, and protect network traffic on AWS.

---

### 2. Designing a Network with Amazon VPC

* Understood that Amazon VPC provides an isolated private network environment on AWS.
* Learned how to select CIDR blocks for VPCs and Subnets.
* Practiced dividing the network as follows:

```text
VPC: 10.11.0.0/16
├── Public Subnet: 10.11.1.0/24
└── Private Subnet: 10.11.2.0/24
```

* Understood that each Subnet belongs to only one Availability Zone.
* Learned how to select non-overlapping CIDR ranges in preparation for connecting multiple VPCs.
* Distinguished between resources deployed in Public Subnets and Private Subnets.

---

### 3. Public Subnets and Internet Gateways

Completed the following tasks:

* Created an Internet Gateway.
* Attached the Internet Gateway to the VPC.
* Created a Public Route Table.
* Added the following Default Route:

```text
Destination: 0.0.0.0/0
Target: Internet Gateway
```

* Associated the Route Table with the Public Subnet.
* Launched an EC2 Instance with a Public IP.
* Tested SSH and Internet connectivity.

Understood that a Subnet is considered public when its Route Table contains a route to an Internet Gateway. Assigning a Public IP to an EC2 Instance alone is not sufficient when the Route Table has not been configured correctly.

---

### 4. Private Subnets and NAT Gateways

Completed the following tasks:

* Allocated an Elastic IP.
* Created a NAT Gateway in the Public Subnet.
* Created a Private Route Table.
* Configured the Private Subnet's Default Route to the NAT Gateway.
* Tested outbound Internet connectivity from the Private EC2 Instance.

Connection flow:

```text
Private EC2
    ↓
Private Route Table
    ↓
NAT Gateway
    ↓
Internet Gateway
    ↓
Internet
```

Key lessons:

* A NAT Gateway must be located in a Public Subnet.
* A NAT Gateway must be associated with an Elastic IP.
* The Public Subnet containing the NAT Gateway must have a route to an Internet Gateway.
* A NAT Gateway allows a Private EC2 Instance to initiate outbound connections but does not allow the Internet to initiate direct connections to the Instance.

---

### 5. Elastic Network Interfaces and Elastic IPs

#### Elastic Network Interface

Understood that an ENI contains the EC2 Instance's network information:

* Primary Private IP.
* Secondary Private IP.
* MAC Address.
* Security Group.
* Information associated with the Subnet.

#### Elastic IP

Elastic IPs were used to:

* Provide a static Public IP for the NAT Gateway.
* Assign a stable address to the EC2 Instance acting as a Customer Gateway.
* Prevent the Public IP from changing after resources are stopped or restarted.

Key lessons:

* An Elastic IP that is not used correctly may still generate costs.
* In some situations, it must be disassociated before it can be released.
* The list of remaining Elastic IPs should be checked after completing an exercise.

---

### 6. Security with Security Groups

* Understood that a Security Group is associated with an ENI or resource.
* Security Groups operate using a Stateful mechanism.
* When an incoming request is allowed, the corresponding response traffic is automatically allowed.

The following rules were tested:

* TCP 22 for SSH.
* ICMP for connectivity testing.
* UDP 500 for IKE.
* UDP 4500 for NAT Traversal.
* Internal rules between EC2 Instances in the VPC.

Applied principles:

* Open only the required ports.
* Restrict the Source CIDR.
* Avoid using `0.0.0.0/0` for administration ports unless necessary.
* Separate Security Groups according to the role of each resource.

---

### 7. Subnet Control with Network ACLs

* Understood that Network ACLs operate at the Subnet level.
* Network ACLs are Stateless.
* Both Inbound and Outbound Rules must be configured.
* Network ACLs support both `ALLOW` and `DENY`.
* Rules are evaluated in order from the lowest rule number to the highest.

Comparison:

| Security Group | Network ACL |
| --- | --- |
| Operates at the ENI or resource level | Operates at the Subnet level |
| Stateful | Stateless |
| Supports Allow Rules only | Supports Allow and Deny Rules |
| Response traffic does not need to be opened separately | Traffic must be allowed in both directions |
| All rules are evaluated together | Evaluation stops at the first matching rule |

---

### 8. Building an AWS Site-to-Site VPN

The following model was deployed:

```text
Private Network
      ↓
EC2 Customer Gateway
      ↓
Encrypted IPsec Tunnel
      ↓
Virtual Private Gateway
      ↓
AWS VPC
```

The main components included:

* Customer Gateway.
* Virtual Private Gateway.
* Site-to-Site VPN Connection.
* Two IPsec Tunnels.
* Static Routes or Dynamic Routing.
* VPC Route Tables.

Understood that:

* Site-to-Site VPN connects an external private network to an Amazon VPC.
* Data is encrypted while being transmitted through the Internet.
* AWS creates two Tunnels to improve redundancy.
* A Tunnel being in the `UP` state does not guarantee that traffic will work when the Route Table or firewall configuration is incorrect.

---

### 9. Configuring an EC2 Instance as a Customer Gateway

* Used an EC2 Instance with an Elastic IP to simulate a Customer Gateway.
* Disabled Source/Destination Check so the EC2 Instance could forward traffic.
* Enabled IP Forwarding in the operating system.
* Allowed VPN-related ports in the Security Group.
* Added appropriate Routes for the private networks.

The following elements were checked:

* Customer Gateway Public IP.
* Customer Gateway-side network CIDR.
* Amazon VPC CIDR.
* Virtual Private Gateway Attachment.
* Route Tables on both sides.
* Security Groups and Network ACLs.

---

### 10. Configuring Libreswan IPsec

The following files were edited:

* `/etc/ipsec.conf`
* `/etc/ipsec.d/aws.conf`
* `/etc/ipsec.secrets`

The following components were configured:

* IKE for Phase 1 negotiation.
* ESP and encryption algorithms for Phase 2.
* Pre-shared Key.
* Local Subnet and Remote Subnet.
* Tunnel Endpoint.
* Dead Peer Detection.

Commands used for verification:

```bash
sudo systemctl status ipsec
sudo systemctl restart ipsec
sudo ipsec status
sudo ipsec verify
```

---

### 11. Distinguishing IKE Phase 1 and IPsec Phase 2

#### Phase 1

* Authenticates the two VPN Endpoints.
* Negotiates encryption algorithms.
* Establishes an IKE Security Association.
* Uses a Pre-shared Key or Certificate.

#### Phase 2

* Negotiates how the actual data traffic will be protected.
* Defines the Local and Remote Subnets.
* Establishes an IPsec Security Association.
* Uses ESP to encrypt traffic.

Understood that:

* Successful Phase 1 negotiation does not guarantee successful Phase 2 negotiation.
* Both sides must use compatible algorithms and Tunnel parameters.
* Incorrect CIDR blocks or Routes can result in an established Tunnel that still cannot transmit data.

---

## Practical Issues Resolved

### 1. VPN Tunnel Did Not Change to the UP State

The following state was observed:

```text
STATE_MAIN_I1
```

The following possible causes were checked:

* Customer Gateway Public IP.
* Pre-shared Key.
* UDP 500.
* UDP 4500.
* IKE Version.
* Encryption algorithms.
* NAT Traversal.
* Libreswan service.

---

### 2. Security Group Did Not Allow VPN Traffic

Resolution steps:

* Allowed UDP 500 from the appropriate VPN Endpoint.
* Allowed UDP 4500 when NAT Traversal was used.
* Checked the Outbound Rules.
* Avoided opening VPN ports to the entire Internet when the Source could be restricted.

---

### 3. EC2 Instance Could Not Forward Traffic

Possible causes:

* Source/Destination Check had not been disabled.
* IP Forwarding had not been enabled.
* The Route Table did not point to the EC2 Customer Gateway.
* A Security Group or Network ACL blocked the traffic.

The following setting was checked:

```bash
sysctl net.ipv4.ip_forward
```

---

### 4. Incorrect Libreswan Configuration

The issue was related to using:

```text
auth=esp
```

Resolution:

* Checked syntax compatibility with the installed Libreswan version.
* Used `phase2alg` to define the Phase 2 algorithms.
* Compared the configuration with the VPN Configuration downloaded from AWS.
* Restarted the service after making changes.

---

### 5. One-Way Ping

Observed result:

* Ping from one side to the EC2 Instance succeeded.
* The reverse direction did not work.

Troubleshooting process:

* Checked Route Tables in both directions.
* Checked the Local and Remote Subnets in the Libreswan configuration.
* Checked Security Groups.
* Checked Network ACLs.
* Checked IP Forwarding.
* Checked the Phase 2 status.

---

## Skills Developed

* Designing VPCs and dividing CIDR ranges.
* Building Public and Private Subnets.
* Configuring Internet Gateways and NAT Gateways.
* Managing Elastic IPs and ENIs.
* Designing Security Groups according to Least Privilege.
* Configuring Network ACLs.
* Deploying a basic Site-to-Site VPN.
* Using EC2 as a Customer Gateway.
* Installing and verifying Libreswan.
* Troubleshooting routing, firewall, and IPsec issues.

---

## Self-Evaluation

* Developed a stronger understanding of:

  * Amazon VPC.
  * CIDR blocks and Subnets.
  * Route Tables.
  * Internet Gateways.
  * NAT Gateways.
  * Security Groups.
  * Network ACLs.
  * Customer Gateways.
  * Virtual Private Gateways.
  * Site-to-Site VPN.
  * IKE and IPsec.

* Able to:

  * Build a basic VPC architecture.
  * Separate Public and Private Networks.
  * Provide outbound connectivity for Private EC2 Instances.
  * Configure security rules at the resource and Subnet levels.
  * Configure a basic Site-to-Site VPN.
  * Check Tunnel states and identify possible causes of failure.

* Areas for further improvement:

  * Complete bidirectional communication through the VPN.
  * Develop a deeper understanding of Dynamic Routing and BGP.
  * Practice VPN deployment with a real Customer Gateway device.
  * Use VPC Flow Logs to analyze traffic.
  * Optimize NAT Gateway and Elastic IP costs.

---

## Next Steps

* Continue studying the Multi-VPC section of Module 02-02.
* Study the next part of Module 02-03.
* Practice with:

  * AWS Systems Manager Session Manager.
  * Interface VPC Endpoints.
  * VPC Peering.
  * AWS Transit Gateway.
  * Route 53 Resolver.
  * Hybrid DNS.
  * Microsoft Active Directory.

* Compare the following connectivity models:

  * VPC Peering.
  * Transit Gateway.
  * Site-to-Site VPN.
  * AWS Direct Connect.

* Continue improving troubleshooting skills across individual network layers.

---

