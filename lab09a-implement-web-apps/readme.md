# 🌐 Lab 09a – Implement Azure Web Apps

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
In this lab, I explored **Azure App Services** by deploying a PHP-based Azure Web App using a Linux runtime. I configured **deployment slots**, enabled **continuous deployment from GitHub**, performed a **slot swap** from staging to production, and implemented **automatic autoscaling**. This lab demonstrates how organizations can modernize web hosting while maintaining performance, reliability, and deployment safety.

---

## 🎯 Objectives
- Deploy an Azure Web App using App Service (PaaS)  
- Configure and manage deployment slots  
- Enable continuous deployment from an external Git repository  
- Perform a staging-to-production slot swap  
- Configure and test autoscaling based on demand  

---

## 🧠 Key Concepts Reinforced

| Concept | Description |
|------|------------|
| Azure App Service | Fully managed PaaS for hosting web applications without managing servers |
| Web Apps | Azure service for hosting HTTP-based applications using multiple runtimes |
| Deployment Slots | Separate environments (staging, production) for testing and safe deployments |
| Continuous Deployment | Automatically deploys application updates from a source repository |
| Slot Swapping | Seamlessly promotes tested code from staging to production |
| Autoscaling | Dynamically adjusts compute resources based on application demand |

---

## 🧰 Lab Environment & Tools
- **Azure Portal** – https://portal.azure.com  
- **Resource Group:** `az104-rg9`  
- **Region:** East US  
- **Runtime Stack:** PHP 8.2 (Linux)  
- **Pricing Tier:** Premium V3 (P1V3)  
- **Services Used:**  
  - Azure App Service  
  - App Service Plan  
  - Deployment Slots  
  - Azure Load Testing  

---

## 🔧 Tasks Performed

### 1. Created and Configured an Azure Web App
- Provisioned a Linux-based Azure Web App using PHP 8.2
- Deployed the app under a Premium V3 App Service Plan
- Verified successful deployment via the default domain

### 2. Created and Configured a Deployment Slot
- Created a **staging** deployment slot
- Verified that staging had a unique URL separate from production
- Used the slot for pre-production testing

### 3. Configured Continuous Deployment
- Connected the staging slot to an **external GitHub repository**
- Enabled automatic deployment from the `master` branch
- Verified successful deployment by displaying a **Hello World** application

### 4. Swapped Deployment Slots
- Swapped the staging slot with production
- Promoted tested code to production with no downtime
- Verified production now displayed the updated application

### 5. Configured and Tested Autoscaling
- Enabled **automatic scale-out** on the App Service Plan
- Configured burst scaling up to two instances
- Created and executed an Azure Load Test
- Observed real-time metrics such as virtual users and response time

---

## 📈 Outcome Summary
By completing this lab, I successfully deployed and managed an Azure Web App using best practices for modern application hosting. I validated deployment safety using slots, ensured continuous integration through GitHub, and demonstrated scalability through load testing and autoscale configuration.

---

## 🏢 Business Relevance
This lab reflects real-world enterprise scenarios where organizations:
- Migrate legacy on-prem web applications to **Azure PaaS**
- Reduce infrastructure overhead and hardware refresh costs
- Implement **zero-downtime deployments** using staging slots
- Automatically scale applications during traffic spikes
- Improve reliability and deployment confidence through testing and automation

---

## 📸 Screenshots

| Task | Screenshot | Caption |
|------|------------|---------|
| Task 1 - Web App Overview | ![App Overview](https://github.com/user-attachments/assets/11ee1742-3f82-4a54-919f-bcefc4702e28) |  Determines the web app compute, storage, and features. |
| Task 2 - Deployment Slot | ![Deploymen Slots](https://github.com/user-attachments/assets/492543a9-10d4-4ed7-98ee-26c3696c41fd)| Enable you to perform testing prior to making your app available to the public (or your end users).|
| Task 5 - Load Test Metrics | ![Test Run](https://github.com/user-attachments/assets/af64ea14-8fdb-4a09-a283-1a0182830487) | Live metrics observed during load testing |

---

## 🧹 Cleanup
To avoid unnecessary costs, the lab resources should be removed after completion.

- **Azure Portal:**  
  - Select the resource group  
  - Click **Delete resource group**  
  - Enter the resource group name and confirm  

- **Azure PowerShell:**  
  ```powershell
  Remove-AzResourceGroup -Name az104-rg9
  ```
