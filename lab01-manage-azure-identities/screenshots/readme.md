# 🔑 Lab 01 – Manage Microsoft Entra ID Identities  

📚 **Table of Contents**  
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
In this lab, I provision **users and groups** in Microsoft Entra ID, Azure’s identity and access management platform. This is the first step toward building a secure and scalable identity foundation in Azure. By creating internal users, inviting guest users, and grouping them into security groups, the lab highlights how identity objects are structured and managed in a tenant.  

---

## 🎯 Objectives  
- Create and configure internal user accounts with attributes such as job title and department  
- Invite an external guest user into the tenant  
- Create a security group and assign members (internal + external)  
- Compare static vs. dynamic group membership options  

---

## 🧠 Key Concepts Reinforced  

| Concept           | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| Tenant            | A dedicated instance of Microsoft Entra ID for an organization             |
| User Accounts     | Store user data such as UPN, display name, department, and usage location  |
| Guest Users       | External accounts invited to collaborate within the tenant                 |
| Groups            | Collections of users/devices used for access and permission assignment     |
| Static Membership | Administrators manually assign/remove members                              |
| Dynamic Membership| Automatically updates based on user attributes (requires Entra ID P1/P2)   |

---

## 🧰 Lab Environment & Tools  
- **Azure Portal** (https://portal.azure.com)  
- **Microsoft Entra Admin Center**  
- **Resource Scope:** Microsoft Entra ID Tenant  
- **Objects Created:**  
  - User: `az104-user1`  
  - Guest User: invited external account  
  - Group: `IT Lab Administrators`  

---

## 🔧 Tasks Performed  

1. **Created Internal User**  
   - UPN: `az104-user1`  
   - Display Name: `az104-user1`  
   - Job Title: IT Lab Administrator  
   - Department: IT  
   - Usage Location: United States  

2. **Invited External User**  
   - Sent email invitation with welcome message  
   - Assigned attributes: Job Title = IT Lab Administrator, Department = IT  

3. **Created Security Group**  
   - Group Type: Security  
   - Group Name: IT Lab Administrators  
   - Membership: Assigned  
   - Added Members: `az104-user1` and invited guest user  
   - Set self as Group Owner  

---

## 📈 Outcome Summary  
✅ Internal user successfully created with required attributes  
✅ External guest user invited and confirmed in tenant  
✅ Security group provisioned with both internal and external members  
✅ Ownership assigned for administrative management  
✅ Reinforced understanding of identity lifecycles in Microsoft Entra ID  

---

## 🏢 Business Relevance  
Provisioning users and groups in Microsoft Entra ID is a **core responsibility for Azure Administrators and IAM Analysts**. This lab mirrors real-world identity operations:  
- Managing employee and contractor access in a secure manner  
- Organizing users into role-based groups for simplified access control  
- Reducing administrative overhead by planning for dynamic group membership  
- Building the foundation for advanced scenarios like Conditional Access, SSO, and MFA  

---

## 🖼️ Screenshots  

| Step Description                     | Screenshot                                                                                               |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| User `az104-user1` created in Entra ID | ![User Created](https://github.com/miadco/az104-labs/blob/main/lab01-manage-azure-identities/screenshots/lab%201%20t%201.png?raw=true) |
| IT Lab Administrators group with members | ![Group Created](https://github.com/miadco/az104-labs/blob/main/lab01-manage-azure-identities/screenshots/lab%201%20t%202.png?raw=true) |

---

## 🙏 Acknowledgments  
- [AZ-104 Official Microsoft Learning Lab 01 – Manage Microsoft Entra ID Identities](https://microsoftlearning.github.io/AZ-104-MicrosoftAzureAdministrator/Instructions/Labs/LAB_01-Manage_Entra_ID_Identities.html)   
- AI-Supported Documentation: Structured and enhanced with ChatGPT (OpenAI) for clarity and presentation.  
