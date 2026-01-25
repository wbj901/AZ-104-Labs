<!-- README.md -->

# 🧩 Azure Automation Lab – Manage Azure Resources with ARM Templates & Bicep

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

This lab focuses on automating Azure infrastructure deployments using **Azure Resource Manager (ARM) templates** and **Azure Bicep**. By exporting, modifying, and redeploying templates through multiple deployment methods, this lab demonstrates how Infrastructure as Code (IaC) improves consistency, reduces human error, and enables scalable cloud operations.

---

## 🎯 Objectives

* Create and export an Azure Resource Manager (ARM) template from an existing resource
* Modify ARM templates and redeploy resources
* Deploy ARM templates using:

  * Azure Portal
  * Azure PowerShell
  * Azure CLI
* Deploy Azure resources using **Azure Bicep**

---

## 🧠 Key Concepts Reinforced

| Concept                      | Description                                                         |
| ---------------------------- | ------------------------------------------------------------------- |
| Infrastructure as Code (IaC) | Declarative approach to provisioning infrastructure using templates |
| ARM Templates                | JSON-based templates used to deploy Azure resources consistently    |
| Parameters Files             | Separate files used to provide reusable configuration values        |
| Azure Cloud Shell            | Browser-based shell environment for managing Azure resources        |
| Azure PowerShell             | Module-based scripting interface for Azure management               |
| Azure CLI                    | Cross-platform command-line tool for Azure                          |
| Azure Bicep                  | Modern, concise abstraction over ARM templates                      |

---

## 🧰 Lab Environment & Tools

* **Azure Portal**: [https://portal.azure.com](https://portal.azure.com)
* **Azure Subscription**: Required
* **Region**: East US
* **Resource Group**: `az104-rg3`
* **Azure Cloud Shell** (PowerShell & Bash)
* **Tools Used**:

  * ARM Templates (JSON)
  * Azure PowerShell (`Az` module)
  * Azure CLI (`az`)
  * Azure Bicep

---

## 🔧 Tasks Performed

### 🛠️ Task 1: Create and Export an ARM Template

* Created a managed disk (`az104-disk1`) via the Azure Portal
* Exported the disk as an ARM template and parameters file
* Reviewed template structure and parameterization

### ✏️ Task 2: Edit and Redeploy ARM Templates

* Modified the exported ARM template and parameters
* Redeployed a second disk (`az104-disk2`) using **Custom Deployment**
* Reviewed deployment history and inputs within the resource group

### ⚡ Task 3: Deploy ARM Templates Using Azure PowerShell

* Configured Azure Cloud Shell with persistent storage
* Uploaded ARM template and parameters files
* Modified the template to deploy `az104-disk3`
* Deployed using `New-AzResourceGroupDeployment`

### 🖥️ Task 4: Deploy ARM Templates Using Azure CLI

* Switched to Bash in Azure Cloud Shell
* Modified the template to deploy `az104-disk4`
* Deployed using `az deployment group create`

### 📦 Task 5: Deploy Resources Using Azure Bicep

* Uploaded a Bicep file defining a managed disk
* Updated configuration values (name, SKU, size)
* Deployed `az104-disk5` using Azure CLI

---

## 📈 Outcome Summary

This lab successfully demonstrated five different deployment methods for Azure resources using Infrastructure as Code. ARM templates and Bicep enabled repeatable, consistent, and automated deployments across multiple interfaces, reinforcing best practices for modern cloud administration.

---

## 🏢 Business Relevance

Automating Azure deployments provides organizations with:

* Reduced configuration drift and human error
* Faster and repeatable infrastructure provisioning
* Improved governance and compliance
* Scalable deployment strategies across environments
* Foundation for CI/CD and DevOps pipelines

Infrastructure as Code is a critical skill for cloud administrators, security teams, and DevOps engineers managing production Azure environments.

---

## 🖼️ Screenshots

> *Optional section — add screenshots of key steps such as:*

* Managed disk creation
* ARM template export
* PowerShell and CLI deployments
* Bicep deployment results

---

## 🙏 Acknowledgments

Lab content adapted from the official **Microsoft AZ-104: Manage Azure Resources by Using ARM Templates** learning materials.

AI assistance was used to structure, summarize, and document this lab for GitHub portfolio presentation and clarity.

