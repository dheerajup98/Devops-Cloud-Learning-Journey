# Cloud Infrastructure Basics

This document explains the basic concepts behind cloud infrastructure including servers, virtualization, hypervisors, and how cloud virtual machines work in data centers.

---

## 1. Server
A server is a powerful computer designed to provide services such as hosting applications, websites, databases, or files to other computers over a network.

---

## 2. Physical Server
A physical server is the actual hardware machine located inside a data center.  
It contains CPU, RAM, storage, networking interfaces, and power supply.

Example hardware:

- CPU: Intel Xeon / AMD EPYC
- RAM: 64GB – 512GB
- Storage: SSD / NVMe
- Network: High-speed Ethernet

---

## 3. Virtualization
Virtualization is a technology that allows multiple virtual environments to run on a single physical server.

Instead of running only one operating system, the hardware resources are divided so multiple systems can run simultaneously.

Benefits:
- Better resource utilization
- Cost efficiency
- Isolation between workloads
- Scalability

---

## 4. Virtual Machine (VM)
A Virtual Machine is a software-based computer created using virtualization.

Each VM includes:
- Operating System
- Virtual CPU
- Virtual RAM
- Virtual Disk
- Virtual Network Interface

Each VM behaves like an independent computer.

---

## 5. Hypervisor
A hypervisor is the software layer responsible for creating and managing virtual machines.

Architecture:

Physical Server  
↓  
Hypervisor  
↓  
Virtual Machines

Examples:
- VMware ESXi
- KVM
- Microsoft Hyper-V

---

## 6. Data Center
A data center is a facility that houses large numbers of servers and networking equipment.

Components inside a data center include:

- Server racks
- Network switches
- Storage systems
- Power backup (UPS, generators)
- Cooling systems

Cloud providers operate large global data centers.

---

## 7. Physical Server Setup in Data Center

Typical infrastructure setup:

1. Servers mounted in racks
2. Connected to top-of-rack switches
3. Connected to core network switches
4. Connected to the internet backbone
5. Power and cooling systems maintain stability

---

## 8. What Happens When You Launch a Cloud VM

When you create a VM in a cloud platform:

1. Request is sent to cloud control system
2. Scheduler selects an available physical server
3. Hypervisor allocates CPU, RAM, and storage
4. VM is created using an OS image
5. Network is configured

The virtual machine becomes available within seconds.

---

## 9. Accessing a Cloud VM (Network Flow)

When you connect to a cloud VM the request path looks like this:

Laptop  
↓  
ISP Network  
↓  
Internet Backbone  
↓  
Cloud Edge Router  
↓  
Data Center Network  
↓  
Physical Server  
↓  
Hypervisor  
↓  
Virtual Machine

This entire process typically happens within milliseconds.


Today I learned how cloud infrastructure is created in AWS and how DevOps engineers automate this process using Infrastructure as Code (IaC).

## Creating a Virtual Machine in AWS

A virtual machine can be created manually using the AWS Management Console through the **Amazon EC2** service.

Basic steps:
1. Login to AWS Console
2. Navigate to EC2
3. Click **Launch Instance**
4. Choose AMI (Operating System)
5. Select Instance Type
6. Configure Storage, Network, and Security Group
7. Launch Instance

Once launched, AWS allocates compute resources in its data center and assigns details such as:
- Instance ID
- Public IP Address
- Private IP Address
- Instance Status

## Infrastructure Automation

Instead of creating infrastructure manually, DevOps engineers automate the process using tools such as:

- **AWS CLI** – Manage AWS services from the command line
- **AWS CloudFormation (CFT)** – Define infrastructure using YAML/JSON templates
- **AWS CDK** – Define infrastructure using programming languages
- **Terraform** – Popular Infrastructure as Code tool used for multi-cloud environments

## AWS API Concept

All these tools ultimately interact with **AWS APIs**.

When a request is sent to create a resource:

1. **Authentication** – AWS verifies the identity of the user or service making the request.
2. **Authorization** – AWS checks permissions using IAM policies.
3. **API Processing** – AWS processes the request in its data centers.
4. **Resource Provisioning** – The VM or resource is created and details are returned.

Example response may include:
- Instance ID
- Public IP address
- Instance state
- Networking configuration

## Hybrid Cloud Model

Many companies use a **Hybrid Cloud** architecture, which combines:

- On-premise infrastructure (private data center)
- Public cloud services (AWS)

This allows organizations to achieve:
- Better scalability
- Improved security
- Flexible workload management

## Key Takeaway

Behind every click in the AWS console, there is an **API call** that communicates with AWS services to provision infrastructure.

Automation tools make this process faster, scalable, and reliable.

