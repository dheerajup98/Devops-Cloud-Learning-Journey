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

---

## Summary

Cloud computing works by combining:

- Physical servers
- Virtualization
- Hypervisors
- Large-scale data centers
- Automated infrastructure management
