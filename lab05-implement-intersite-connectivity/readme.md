# 🌐 Azure Networking Lab – Implement Intersite Connectivity

## 📚 Table of Contents

- [Overview](#-overview)
- [Objectives](#-objectives)
- [Key Concepts Reinforced](#-key-concepts-reinforced)
- [Lab Environment & Tools](#-lab-environment--tools)
- [Tasks Performed](#-tasks-performed)
- [Outcome Summary](#-outcome-summary)
- [Business Relevance](#-business-relevance)
- [Screenshots](#-screenshots)
- [Acknowledgments](#-acknowledgments)

---

## 📌 Overview

This lab focuses on implementing **secure intersite connectivity between Azure virtual networks** using **virtual network peering**. The lab validates cross-network communication, analyzes connectivity using Azure-native diagnostic tools, and introduces **custom routing** to control traffic flow.

The scenario mirrors a real-world enterprise environment where isolated workloads—such as **core IT services** and **manufacturing systems**—must communicate securely while maintaining logical separation.

---

## 🎯 Objectives

- Deploy virtual machines in separate Azure virtual networks  
- Implement virtual network peering for private intersite connectivity  
- Validate connectivity using Azure Network Watcher  
- Test communication using Azure PowerShell  
- Create and associate user-defined routes (UDRs)  

---

## 🧠 Key Concepts Reinforced

| Concept | Description |
|------|------------|
| Virtual Network Peering | Private connectivity between Azure VNets |
| Network Isolation | Logical separation of workloads by function |
| Microsoft Backbone | Peered traffic remains on Microsoft’s global network |
| Network Watcher | Azure-native networking diagnostics and testing |
| User-Defined Routes (UDRs) | Custom routing to override system routes |
| Virtual Network Appliance (NVA) | Centralized routing and traffic inspection |

---

## 🧰 Lab Environment & Tools

- **Azure Portal**: https://portal.azure.com  
- **Azure Subscription**: Required  
- **Region**: East US  
- **Resource Group**: `az104-rg5`  

### Services Used
- Azure Virtual Machines  
- Azure Virtual Networks  
- Virtual Network Peering  
- Azure Network Watcher  
- Route Tables (UDRs)  
- Azure PowerShell  

---

## 🔧 Tasks Performed

### 🏗️ Task 1: Create Core Services Virtual Network and VM

- Created **CoreServicesVnet** with address space `10.0.0.0/16`
- Deployed **CoreServicesVM** in subnet:
  - `Core` (`10.0.0.0/24`)
- Disabled public inbound connectivity
- Created the virtual network during VM deployment

---

### 🏭 Task 2: Create Manufacturing Virtual Network and VM

- Created **ManufacturingVnet** with address space `172.16.0.0/16`
- Deployed **ManufacturingVM** in subnet:
  - `Manufacturing` (`172.16.0.0/24`)
- Ensured no public inbound access

---

### 🔍 Task 3: Test Connectivity with Network Watcher (Pre-Peering)

- Used **Connection Troubleshoot** in Azure Network Watcher  
- Tested TCP connectivity on port **3389**  
- Confirmed connectivity status was **Unreachable**, validating network isolation  

---

### 🔗 Task 4: Configure Virtual Network Peering

- Created **bi-directional peering** between:
  - CoreServicesVnet
  - ManufacturingVnet
- Enabled VNet access and forwarded traffic
- Verified peering state showed **Connected**

---

### 💻 Task 5: Test Connectivity Using Azure PowerShell

- Retrieved the private IP address of **CoreServicesVM**
- Used **Run Command** on **ManufacturingVM**
- Executed the following command:

```powershell
Test-NetConnection <CoreServicesVM-Private-IP> -Port 3389 
```

---

### 🚦 Task 6: Create and Associate a Custom Route

- Created a perimeter subnet: `10.0.1.0/24`
- Deployed route table **rt-CoreServices**
- Created a user-defined route:
  - Address prefix: `10.0.0.0/16`
  - Next hop type: Virtual appliance
  - Next hop IP: `10.0.1.7`
- Associated the route table with the Core subnet
- Simulated routing through a future NVA for centralized traffic inspection

---

### 📈 Outcome Summary

This lab demonstrated how to securely connect isolated Azure virtual networks using virtual network peering, validate connectivity using Azure-native diagnostic tools, and control routing behavior using user-defined routes.

The resulting architecture reflects enterprise networking best practices for segmentation, security, and scalability.

---

### 🏢 Business Relevance

Implementing intersite connectivity allows organizations to:

  - Maintain workload isolation while enabling required communication
  - Reduce latency by leveraging Microsoft’s global backbone
  - Eliminate complexity associated with site-to-site VPNs
  - Centralize traffic inspection using NVAs and UDRs
  - Support scalable, enterprise-grade Azure network designs

---

## 🖼️ Screenshots

| Step Description | Screenshot |
|------------------|------------|
| **Task 3 –  Network Watcher connectivity test** <br> Verify that resources in peered virtual networks can communicate with each other. | ![Task 1](https://github.com/user-attachments/assets/6b764562-881d-4b6a-bee4-2a71e722606c) |
| **Task 5 – PowerShell-based connectivity validation.** <br> Test the connection to the CoreServicesVM from the ManufacturingVM. | ![Task 5](https://github.com/user-attachments/assets/06bde20f-2d1b-46c1-8645-46c4834f013a) |
| **Task 4 – Create a custom route** <br> Control network traffic between the perimeter subnet and the internal core services subnet | ![Task 2b](https://github.com/user-attachments/assets/b4b525f0-bac7-4e1d-bab8-1f91e4c8d6ac) |


---

## 🙏 Acknowledgments

Lab content adapted from the official **Microsoft AZ-104: Implement Virtual Networking** learning materials.

AI assistance was used to structure, summarize, and document this lab for GitHub portfolio presentation and clarity.

