# 🛡️ Lab 10 – Implement Data Protection

## 📚 Table of Contents
- [Overview](#-overview)
- [Objectives](#-objectives)
- [Key Concepts Reinforced](#-key-concepts-reinforced)
- [Lab Environment & Tools](#-lab-environment--tools)
- [Tasks Performed](#-tasks-performed)
- [Outcome Summary](#-outcome-summary)
- [Business Relevance](#-business-relevance)
- [Screenshots](#-screenshots) 
- [Cleanup](#-cleanup)


---

## 📌 Overview
In this lab, I implemented **data protection and disaster recovery solutions** for Azure virtual machines using **Azure Backup** and **Azure Site Recovery (ASR)**. I deployed infrastructure using ARM templates, configured Recovery Services vaults, enabled VM-level backups, monitored backup jobs, and configured cross-region replication for disaster recovery scenarios.

This lab demonstrates how organizations protect critical workloads against **accidental deletion, data corruption, and regional outages**.

---

## 🎯 Objectives
- Deploy Azure infrastructure using ARM templates  
- Create and configure Recovery Services vaults  
- Configure Azure virtual machine backups and retention policies  
- Monitor Azure Backup jobs and diagnostics  
- Enable cross-region VM replication using Azure Site Recovery  

---

## 🧠 Key Concepts Reinforced

| Concept | Description |
|------|------------|
| Azure Backup | Native Azure service for backing up VMs, files, and workloads |
| Recovery Services Vault | Centralized storage and management for backup and recovery data |
| Backup Policies | Define backup frequency, retention, and recovery points |
| Soft Delete | Protects backup data from accidental or malicious deletion |
| Azure Site Recovery | Disaster recovery solution for replicating workloads across regions |
| Cross-Region Restore | Allows restore operations from paired Azure regions |

---

## 🧰 Lab Environment & Tools
- **Azure Portal** – https://portal.azure.com  
- Regions Used: **East US** and **West US**  
- Resource Groups:
  - `az104-rg-region1`
  - `az104-rg-region2`
- Services Used:
  - Azure Virtual Machines  
  - Recovery Services Vault  
  - Azure Backup  
  - Azure Site Recovery  
  - Azure Storage Account  

---

## 🔧 Tasks Performed

### Task 1 – Provision Infrastructure with ARM Template
- Deployed a virtual network and virtual machine using a provided ARM template.
- Validated successful deployment of `az104-10-vm0` in **East US**.

---

### Task 2 – Create and Configure a Recovery Services Vault
- Created a Recovery Services vault (`az104-rsv-region1`) in **East US**.
- Verified **Geo-redundant storage (GRS)** configuration.
- Reviewed and confirmed **Soft Delete** protection (14-day retention).

---

### Task 3 – Configure Azure VM-Level Backup
- Created a **custom backup policy**:
  - Daily backups at 12:00 AM
  - 2-day instant recovery snapshot retention
- Enabled VM backup for `az104-10-vm0`.
- Initiated an on-demand backup and validated backup status.

---

### Task 4 – Monitor Azure Backup
- Deployed an Azure Storage account for diagnostics.
- Configured Recovery Services vault **diagnostic settings** to archive:
  - Azure Backup job data
  - Azure Backup alerts
  - Azure Site Recovery jobs and events
- Reviewed backup job details and status.

---

### Task 5 – Enable Virtual Machine Replication
- Created a second Recovery Services vault (`az104-rsv-region2`) in **West US**.
- Enabled Azure Site Recovery replication for `az104-10-vm0`.
- Verified replication health and synchronization status.
- Confirmed VM protection status after initial sync.

---

## 📈 Outcome Summary
By completing this lab, I successfully implemented **backup, monitoring, and disaster recovery** for Azure virtual machines. I validated Azure’s built-in protection mechanisms and ensured workloads could be restored or failed over in the event of data loss or regional outages.

---

## 🏢 Business Relevance
Organizations rely on Azure Backup and Site Recovery to:
- Protect workloads against **ransomware, accidental deletion, and corruption**
- Meet **business continuity and disaster recovery (BCDR)** requirements
- Reduce downtime with **cross-region replication**
- Centralize backup management with **Recovery Services vaults**
- Meet compliance and data protection standards

This lab mirrors real-world enterprise practices for securing cloud infrastructure.

---

## 📸 Screenshots

| Task | Screenshot | Caption |
|------|------------|---------|
| **Task 2 – Recovery Service Vault** | ![Recovery Service Fault](https://github.com/user-attachments/assets/3d07d5b1-2e9a-4418-a8bc-4f0bbcd3140b) | A Recovery Services vault provides storage for the virtual machine data. |
| **Task 5 – Virtual Machine Replication** | ![VM Replication](https://github.com/user-attachments/assets/7d531cc8-5099-4feb-80f9-10b2ce1e5436) | Note that the status will show the synchronization (starting at 0%) status and ultimately show **Protected** after the initial synchronization completes |


---

## 🧹 Cleanup
If using your own subscription, delete lab resources to avoid unnecessary costs.

**Options:**
- Azure Portal: Delete the resource groups
- PowerShell:
  ```powershell
  Remove-AzResourceGroup -Name resourceGroupName

