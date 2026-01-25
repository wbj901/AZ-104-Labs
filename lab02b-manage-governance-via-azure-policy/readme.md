# 🎩 Hybrid Identity Lab – Phase 2b: Configure Azure Policy

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
In this lab, I configure governance in Azure by assigning and testing Azure Policy, reviewing compliance, and applying resource locks. The purpose is to enforce organizational standards, evaluate compliance results, and implement safeguards against accidental changes or deletions.

---

## 🎯 Objectives
- Assign built-in Azure Policy definitions  
- Evaluate policy compliance across resources  
- Test enforcement by creating non-compliant resources  
- Apply resource locks to prevent accidental deletions  

---

## 🧠 Key Concepts Reinforced

| Concept                | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| Azure Policy            | Service that enforces organizational standards and evaluates compliance    |
| Built-in Policy         | Predefined policies like requiring tags or restricting resource locations  |
| Compliance Evaluation   | Review of Azure resources against assigned policies                        |
| Resource Lock           | Prevents accidental changes or deletion of critical resources              |
| Governance              | Centralized control over resources, cost, and security                     |

---

## 🧰 Lab Environment & Tools
- Azure Portal (https://portal.azure.com)  
- Resource Group: **az104-rg2**  
- Built-in Policy: **Require a tag and its value on resources**  
- Resource Lock: **rg-lock** applied to the resource group  

---

## 🔧 Tasks Performed
1. Created a new resource group **az104-rg2** with a `Cost Center` tag.  
2. Assigned the **Require a tag and its value on resources** built-in policy.  
3. Attempted to create non-compliant resources to test enforcement.  
4. Added tags to bring resources into compliance.  
5. Configured a **Delete lock** on the resource group to prevent accidental removal.  

---

## 📈 Outcome Summary
The lab successfully demonstrated how to enforce governance at scale in Azure. Policies ensured that all resources must include required tags, preventing creation of non-compliant resources. Compliance checks provided visibility into adherence, while resource locks safeguarded critical infrastructure from accidental deletion.  

---

## 🏢 Business Relevance
Strong governance in Azure environments ensures:  
- Cost management by enforcing required tags like Cost Center or Department  
- Regulatory compliance through standardized rules across subscriptions  
- Protection of mission-critical workloads from accidental removal  
- Alignment of IT resources with business and security requirements  

---

## 🖼️ Screenshots

| Step Description | Screenshot |
|------------------|------------|
| **Task 1 – Resource Group Setup** <br> Creating a new resource group (`az104-rg2`) with Cost Center tag applied. | ![Task 1](https://github.com/user-attachments/assets/28887d1d-e3a6-4305-8ed1-f01824293f07) |
| **Task 2 – Enforce Tagging** <br> Assigning the built-in policy “Require a tag and its value on resources” at the subscription and resource group scope. | ![Task 2a](https://github.com/user-attachments/assets/3a2368a6-b7be-4d30-bc33-f3f2a889ab7d) |
| **Task 3 – Policy Assignment (Review + Create)** <br> Remediate any non-compliant resources. Make any child resources of a resource group inherit the `Cost Center` tag that was defined on the resource group. | ![Task 2b](https://github.com/user-attachments/assets/aa8f92c8-756d-41dd-a913-b3e9b8214394) |
| **Task 4 – Resource Lock** <br> Adding a Delete lock (`rg-lock`) at the resource group level to prevent accidental deletion. | ![Task 3](https://github.com/user-attachments/assets/db80a28f-55e8-4f0c-ac59-50d5fcae8f6d) |

---

## 🙏 Acknowledgments
Lab instructions adapted from the official [AZ-104 Microsoft Learning Lab: Manage Governance via Azure Policy](https://microsoftlearning.github.io/AZ-104-MicrosoftAzureAdministrator/Instructions/Labs/LAB_02b-Manage_Governance_via_Azure_Policy.html).  
AI assistance was used to structure, document, and refine this lab for clarity and presentation.
