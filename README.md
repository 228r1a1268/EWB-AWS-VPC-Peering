**AWS VPC Peering: Private Connectivity Between Two VPCs**

EWB AWS Internship Project
Author: Avinash Vishwakarma
Project Status: Completed

**Overview:**

This project demonstrates how to establish private communication between two Amazon Virtual Private Clouds (VPCs) using AWS VPC Peering.

Two VPCs with non-overlapping IPv4 CIDR blocks were configured with private application instances. A bastion host in VPC A provided SSH access to the application instances. Route tables and security group rules were configured to enable and control private communication between the VPCs.

Connectivity was verified through SSH and ICMP ping tests. A controlled ICMP failure and recovery test demonstrated the impact of security group rules on network connectivity.

Objectives:

Create two VPCs with non-overlapping CIDR blocks.

Configure public and private subnets.

Establish a VPC Peering connection.

Configure route tables for communication in both directions.

Control SSH and ICMP traffic using security groups.

Validate private connectivity between application instances.

Perform a controlled connectivity failure and recovery test.

Clean up project resources after testing.

**AWS Services and Technologies :**

Amazon VPC: Isolated virtual networks.

VPC Peering: Private communication between the two VPCs.

Amazon EC2: Bastion host and application instances.

Route Tables: Routing within each VPC and across the peering connection.

Security Groups: Inbound traffic control for SSH and ICMP.

Internet Gateway: Internet connectivity for the bastion's public subnet.

Amazon Linux 2023 and OpenSSH: Operating environment and remote administration.

ICMP and ping: Connectivity testing and troubleshooting.
Controlled Failure and Recovery

The inbound All ICMP - IPv4 rule was temporarily removed from ewb-sg-app-b. Ping requests from App-A to App-B then failed. After the rule was restored with the source restricted to 10.10.2.10/32, connectivity was successfully re-established.

This demonstrated that correct routing alone is not sufficient when security group rules block the required traffic.

**Security Considerations:**

Application instances communicated using private IP addresses.

SSH access was controlled through security group rules.

ICMP access was restricted to the required source during the recovery test.

Private keys, passwords, and AWS access credentials must not be committed to this repository.


**Cleanup**:

After testing and evidence collection, the project EC2 instances, EBS volumes, VPC Peering connection, project subnets, and project VPCs were removed. Remaining project resources were checked as part of the cleanup process.


**Learning Outcomes**:

This project provided hands-on experience with AWS networking, subnetting, route tables, VPC Peering, security groups, SSH administration, connectivity testing, troubleshooting, and cloud resource cleanup.

**Project Report and Evidence**:

The repository contains the project report and supporting screenshots documenting the architecture, network configuration, connectivity tests, controlled failure and recovery, and resource cleanup.
