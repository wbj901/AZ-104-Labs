# 🌐 Azure Networking Lab – Implement Virtual Networking

## 📚 Table of Contents

* [Overview](#-overview)
* [Objectives](#-objectives)
* [Key Concepts Reinforced](#-key-concepts-reinforced)
* [Lab Environment & Tools](#-lab-environment--tools)
* [Tasks Performed](#-tasks-performed)
* [Outcome Summary](#-outcome-summary)
* [Business Relevance](#-business-relevance)
* [Screenshots](#-screenshots)
* [Acknowledgments](#-acknowledgments)

---

## 📌 Overview

This lab introduces core **Azure Virtual Networking** concepts, including virtual networks, subnet design, network security groups (NSGs), application security groups (ASGs), and Azure DNS. The goal is to design scalable, secure networking foundations that support both current workloads and future organizational growth.

---

## 🎯 Objectives

* Design and deploy Azure virtual networks with scalable IP addressing
* Create and configure subnets to support growth
* Deploy and associate Network Security Groups (NSGs)
* Implement Application Security Groups (ASGs) for traffic control
* Configure public and private Azure DNS zones

---

## 🧠 Key Concepts Reinforced

| Concept                          | Description                                                                 |
| -------------------------------- | --------------------------------------------------------------------------- |
| Virtual Network (VNet)           | Logical isolation of Azure resources within a private network               |
| Subnetting                       | Segmenting a VNet into smaller address spaces for organization and security |
| IP Address Planning              | Designing non-overlapping address ranges to support growth                  |
| Network Security Group (NSG)     | Controls inbound and outbound traffic at subnet or NIC level                |
| Application Security Group (ASG) | Groups VMs by workload for simplified security rules                        |
| Azure DNS                        | Managed DNS service for public and private name resolution                  |

---

## 🧰 Lab Environment & Tools

* **Azure Portal**: [https://portal.azure.com](https://portal.azure.com)
* **Azure Subscription**: Required
* **Region**: East US
* **Resource Group**: `az104-rg4`
* **Services Used**:

  * Azure Virtual Networks
  * Network Security Groups (NSGs)
  * Application Security Groups (ASGs)
  * Azure DNS (Public & Private Zones)

---

## 🔧 Tasks Performed

### 🏗️ Task 1: Create a Virtual Network and Subnets (Portal)

* Created **CoreServicesVnet** with address space `10.20.0.0/16`
* Designed subnets for scalability:

  * `SharedServicesSubnet` (`10.20.10.0/24`)
  * `DatabaseSubnet` (`10.20.20.0/24`)
* Exported the VNet configuration as an ARM template

### 📄 Task 2: Deploy a Virtual Network Using ARM Templates

* Modified exported ARM template to create **ManufacturingVnet**
* Updated address space to `10.30.0.0/16`
* Created subnets sized for IoT and manufacturing growth:

  * `SensorSubnet1` (`10.30.20.0/24`)
  * `SensorSubnet2` (`10.30.21.0/24`)
* Deployed the template using **Custom Deployment**

### 🔐 Task 3: Configure NSG and ASG Communication

* Created an **Application Security Group** (`asg-web`)
* Created and associated an **NSG** (`myNSGSecure`) with `SharedServicesSubnet`
* Configured inbound rule allowing HTTP/HTTPS from ASG
* Configured outbound rule denying internet access

### 🌍 Task 4: Configure Azure DNS Zones

#### Public DNS Zone

* Created public DNS zone `contoso.com`
* Added A record for `www.contoso.com`
* Verified name resolution using `nslookup`

#### Private DNS Zone

* Created private DNS zone `private.contoso.com`
* Linked zone to **ManufacturingVnet**
* Added A record for internal VM name resolution

---

## 📈 Outcome Summary

This lab successfully demonstrated how to design and implement a secure, scalable Azure networking architecture. Virtual networks were planned with growth in mind, security was enforced using NSGs and ASGs, and DNS services enabled both public and private name resolution.

---

## 🏢 Business Relevance

Effective Azure networking enables organizations to:

* Support scalable application growth without readdressing networks
* Improve security using layered network controls
* Simplify traffic management through logical grouping (ASGs)
* Enable reliable name resolution for both public-facing and internal workloads
* Establish a strong foundation for hybrid and enterprise cloud architectures

---

## 🖼️ Screenshots

> *Optional section — add screenshots of:*

* Virtual network and subnet configuration
* ARM template modifications
* NSG inbound/outbound rule configuration
* DNS zone records and resolution testing

---

## 🙏 Acknowledgments

Lab content adapted from the official **Microsoft AZ-104: Implement Virtual Networking** learning materials.

AI assistance was used to structure, summarize, and document this lab for GitHub portfolio presentation and clarity.

