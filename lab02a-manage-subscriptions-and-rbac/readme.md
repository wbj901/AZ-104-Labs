# 🛡️ Lab 02a – Manage Subscriptions and RBAC  

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
In this lab, I configure **role-based access control (RBAC)** in Azure. The lab focuses on using permissions and scopes to manage access, simplifying subscription management with **management groups**, and enforcing the principle of least privilege through custom RBAC roles.  

This scenario represents how an Azure Administrator can delegate responsibilities to teams such as Help Desk engineers while maintaining tight security controls across multiple subscriptions.  

⏱️ Estimated Time: ~30 minutes  
🌍 Region: East US (steps adaptable to other regions)  

---

## 🎯 Objectives  
- Create and configure a **management group** to organize subscriptions  
- Review and assign a built-in Azure role  
- Create a **custom RBAC role** with least privilege  
- Monitor role assignments using the **Activity Log**  

---

## 🧠 Key Concepts Reinforced  

| Concept | Description |  
|---------|-------------|  
| Management Groups | Logical containers that help organize subscriptions and apply policies/roles at scale |  
| Root Management Group | Built-in container that all management groups and subscriptions roll up to |  
| RBAC (Role-Based Access Control) | Access management system defining permissions at scope levels |  
| Built-in Roles | Predefined roles like Owner, Contributor, Reader, and specialized roles such as VM Contributor |  
| Custom Roles | JSON-defined roles allowing tailored permissions (Actions, NotActions, AssignableScopes) |  
| Activity Log | Portal feature that records subscription-level events, including role assignments |  

---

## 🧰 Lab Environment & Tools  
- **Azure Portal** (https://portal.azure.com)  
- **Microsoft Entra Admin Center**  
- **Objects Created/Configured:**  
  - Management Group: `az104-mg1`  
  - Built-in Role Assignment: Virtual Machine Contributor  
  - Custom Role: `Custom Support Request`  

---

## 🔧 Tasks Performed  

1. **Implemented Management Groups**  
   - Enabled access management for subscriptions in Entra ID tenant properties  
   - Created a new management group:  
     - **ID:** `az104-mg1`  
     - **Display Name:** `az104-mg1`  

2. **Reviewed and Assigned a Built-in Role**  
   - Explored built-in roles available in Azure  
   - Assigned **Virtual Machine Contributor** role to the `helpdesk` group at the management group scope  
   - Confirmed assignment in IAM Role Assignments tab  

3. **Created a Custom RBAC Role**  
   - Cloned **Support Request Contributor** role  
   - Modified permissions to exclude **“Register Support Resource Provider”**  
   - Named role: **Custom Support Request**  
   - Scoped assignment to `az104-mg1` management group  
   - Reviewed and validated JSON definition of the custom role  

4. **Monitored Role Assignments with Activity Log**  
   - Accessed the Activity Log for `az104-mg1`  
   - Filtered for role assignment events  
   - Verified successful creation of the custom role and Help Desk group assignment  

---

## 📈 Outcome Summary  
✅ Management group created and configured (`az104-mg1`)  
✅ Built-in **VM Contributor** role assigned to Help Desk group  
✅ Custom RBAC role (`Custom Support Request`) created and applied  
✅ Role assignments tracked through the Activity Log  
✅ Reinforced security best practices: least privilege, group-based role assignments, and governance at scale  

---

## 🏢 Business Relevance  
Role-based access control (RBAC) is one of the most critical aspects of **Azure governance and security**. This lab reflects real-world scenarios where organizations need to:  
- Organize subscriptions for simpler management with **management groups**  
- Assign **least privilege** access to support teams  
- Implement **custom RBAC roles** to align with business requirements  
- Track and audit permissions using the **Activity Log**  

These skills are directly relevant to **cloud administrators, IAM specialists, and governance/compliance analysts**.  

---

## 🖼️ Screenshots  

| Step Description                     | Screenshot                                                                                               |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Created Management Group `az104-mg1` | ![Management Group](https://github.com/user-attachments/assets/3ae4f977-8c8f-45e2-9320-8e1d9046f03e) |
| Assigned Built-in VM Contributor Role | ![Built-in Role Assignment](https://github.com/user-attachments/assets/104b9405-4553-4222-9cbb-46500e6d6b0f) |
| Created Custom RBAC Role | ![Custom Role](https://github.com/user-attachments/assets/5e3666ad-3c48-47dd-9dd4-71e1770aae88) |
| Verified Role Assignments in Activity Log | ![Activity Log](https://github.com/miadco/az104-labs/blob/main/lab02a-manage-subscriptions-and-rbac/screenshots/lab%202a%20t%204.png?raw=true) |

---

## 🙏 Acknowledgments  
- [AZ-104 Official Microsoft Learning Lab 02a – Manage Subscriptions and RBAC](https://microsoftlearning.github.io/AZ-104-MicrosoftAzureAdministrator/Instructions/Labs/LAB_02a_Manage_Subscriptions_and_RBAC_Entra.html)  
- AI-Supported Documentation: Structured and enhanced with ChatGPT (OpenAI) for clarity and presentation.  
