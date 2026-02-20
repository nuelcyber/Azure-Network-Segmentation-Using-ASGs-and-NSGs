# Azure Network Segmentation Using ASGs and NSGs

## Overview

This lab demonstrates the implementation of secure virtual networking in Microsoft Azure using Network Security Groups (NSGs) and Application Security Groups (ASGs).  

The objective was to design and enforce controlled network access between two server tiers: Web Servers and Management Servers, in accordance with best security practices


## Lab Scenario

The organization requires:

- Two groups of servers:
  - Web Servers
  - Management Servers
- Each group must be placed in its own Application Security Group (ASG).
- RDP access must be allowed only to Management Servers.
- Web Servers must display the IIS default web page when accessed from the Internet.
- Network Security Group (NSG) rules must enforce traffic control.



## Lab Objectives

### Exercise 1: Create the Virtual Networking Infrastructure  
### Exercise 2: Deploy Virtual Machines and Test Network Filters  



# Virtual Networking Infrastructure

## Task 1: Create a Virtual Network

**Steps performed:**

1. Created a Virtual Network (VNet).
2. Configured one subnet within the VNet.
3. Selected the appropriate Azure region.
4. Verified successful deployment.

<p align="center"><strong>Figure 1: Creating a Virtual Network</strong></p>

<p align="center">
  <img src="images/senior-admins.png" width="700" height="400">
</p>

**Purpose:**  
Establishes an isolated cloud network infrastructure to host virtual machines securely.



## Task 2: Create Application Security Groups

**Steps performed:**

1. Created an ASG named **WebServers-ASG**.
2. Created an ASG named **ManagementServers-ASG**.
3. Verified that both ASGs were successfully provisioned.

<p align="center"><strong>Figure 2: Creating Application Security Groups </strong></p>

<p align="center">
  <img src="images/senior-admins.png" width="700" height="400">
</p>

**Purpose:**  
Enables logical grouping of virtual machines for simplified and scalable security rule management.


## Task 3: Create and Associate Network Security Group

**Steps performed:**

1. Created a Network Security Group (NSG).
2. Configured inbound security rule settings.
3. Associated the NSG with the subnet created earlier.

<p align="center"><strong>Figure 3: Creating Network Security Groups </strong></p>

<p align="center">
  <img src="images/senior-admins.png" width="700" height="400">
</p>

**Purpose:**  
Applies centralized network filtering policies at the subnet level.



## Task 4: Configure Inbound NSG Security Rules

**Steps performed:**

1. Created inbound rule to allow HTTP (Port 80) traffic to **WebServers-ASG**.
2. Created inbound rule to allow RDP (Port 3389) traffic to **ManagementServers-ASG**.
3. Verified priority and source settings.
4. Ensured default deny rule blocks unauthorized traffic.

<p align="center"><strong>Figure 4: Configuring NSG Rules</strong></p>

<p align="center">
  <img src="images/senior-admins.png" width="700" height="400">
</p>

**Purpose:**  
Implements fine-grained access control using ASG-based targeting and enforces the principle of least privilege.



# Exercise 2: Deploy Virtual Machines and Test Network Filters

**Steps performed:**

1. Deployed Web Server VM and assigned it to **WebServers-ASG**.
2. Installed IIS role on the Web Server.
3. Deployed Management Server VM and assigned it to **ManagementServers-ASG**.
4. Tested RDP access:
   - Successful connection to Management Server.
   - RDP access blocked to Web Server.
5. Tested web access:
   - IIS default page successfully displayed from internet browser.

<p align="center"><strong>Figure 5: Senior Admins Group Creation</strong></p>

<p align="center">
  <img src="images/senior-admins.png" width="700" height="400">
</p>

# Security Concepts Demonstrated

- Network segmentation using Virtual Networks
- Application Security Group-based rule targeting
- Role-based traffic filtering with NSGs
- Principle of Least Privilege
- Controlled administrative access (RDP restriction)
- Internet-facing web service configuration (HTTP only)



# Key Learning Outcomes

- Designed secure multi-tier network architecture in Azure.
- Implemented subnet-level network security enforcement.
- Used ASGs to simplify scalable rule management.
- Applied NSG priority and rule evaluation logic.
- Tested and validated network access controls effectively.



# Conclusion

This lab demonstrates practical implementation of Azure network security controls using NSGs and ASGs to protect cloud workloads. By enforcing restricted administrative access and controlled internet exposure, the lab reflects real-world enterprise security design principles.

