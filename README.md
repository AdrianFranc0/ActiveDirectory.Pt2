# ActiveDirectory.Pt2
This project is a continuation of my original Active Directory lab where I built a Windows Server Domain Controller from scratch. In Part 2, I focused on simulating real-world helpdesk and junior system administrator tasks, including user and group management, account provisioning, and permissions control using Organizational Units (OUs) and Group Policy Objects (GPOs).

This phase highlights key Active Directory operations that reflect day-to-day responsibilities in enterprise IT support environments.

---

<p align="center">
### User Accounts Created in Active Directory
<p align="center"> <img src="https://i.imgur.com/2QjRx4S.png" width="600" style="height:auto;" alt="AD User List"> </p>
Description:
As part of the initial domain setup, user accounts were created in Active Directory to simulate employees from different departments.
These users were added using a powershell script to reflect typical naming conventions and user provisioning tasks carried out by helpdesk or sysadmin staff.
This foundational step allows for user specific policy testing, group assignments, and domain logins throughout the lab.

---

### OU Structure and User Organization

<p align="center">
  <img src="https://i.imgur.com/PuNTmTr.png" width="600" style="height:auto;" alt="OU Structure">
</p>

> **Description**:  
> This screenshot shows a clean OU structure organized by department (IT, SOC, HR, and Workstations). Creating Organizational Units in Active Directory is a best practice that improves directory management, policy targeting, and delegation of permissions. Users were manually organized into their corresponding OUs to simulate a realistic environment.

---

### Reset a User Password

<p align="center">
  <img src="https://i.imgur.com/DIn3Z22.png" width="600" style="height:auto;" alt="Password Reset">
</p>

> **Description**:  
> Resetting a user’s password is one of the most frequent IT helpdesk tasks, typically done when a user forgets their credentials or during onboarding.  
> In this screenshot, a password reset was initiated for a test user. In a real-world environment, it's best practice to check **“User must change password at next logon”** to ensure the user sets a secure, personal password.  
> Additionally, if the account had been locked due to failed login attempts, **“Unlock the user’s account”** would be checked.  
> This process is critical for maintaining secure but accessible accounts.

---

### Disable a User Account

<p align="center">
  <img src="https://i.imgur.com/jHdWqev.png" width="600" style="height:auto;" alt="Disabled User">
</p>

> **Description**:  
> In an enterprise environment, disabling user accounts is a common IT helpdesk task, especially during employee terminations, extended leave, or security incidents.  
> This screenshot shows a disabled user account. The account was disabled to simulate offboarding or temporary deactivation. **As you can see with the down arrow.** This process is critical to protect systems from unauthorized access while preserving account data for audit or reactivation purposes.

---

### Create a Security Group + Assign Permissions

<p align="center">
  <img src="https://i.imgur.com/3xxkSAi.png" width="600" style="height:auto;" alt="Group Membership">
</p>

> **Description**:  
> Security groups are used to manage user access to shared resources like folders and printers.  
> A group named **“Shared Drive Access”** was created, and the user **ITuser01** was added to it. This allows the user to inherit access to any resources assigned to the group.  
> Placing the group in an Organizational Unit (OU) helps with structure and makes it easier to manage permissions or apply Group Policies later.

---

### Shared Folder with Group Permissions

<p align="center">
  <img src="https://i.imgur.com/Fovz6Ud.png" width="600" style="height:auto;" alt="Shared Folder Permissions">
</p>

> **Description**:  
> In this step, a shared folder named **SharedDocs** was created and permissions were assigned to the **Shared Drive Access** group.  
> This simulates a real-world scenario where access to network folders is controlled by group membership. Managing permissions through groups is more scalable and secure than assigning them to users individually.

---

### Join Workstation to Domain

<p align="center">
  <img src="https://i.imgur.com/eAkAmNa.png" width="600" style="height:auto;" alt="Domain Joined Confirmation">
</p>

> **Description**:  
> Joining a workstation to the domain allows it to receive group policies, authenticate against Active Directory, and access domain resources.  
> In this screenshot, **Client1** was successfully joined to the domain `mydomain.com`, and logged in as **ITuser01**, confirming that the domain join process and user profile setup were successful.

---

### Group Policy Configuration – Password Policy

<p align="center">
  <img src="https://i.imgur.com/koB2YLZ.png" width="600" style="height:auto;" alt="GPO Password Policy">
</p>

> **Description**:  
> This Group Policy Object (GPO) was created to enforce password security standards.  
> The policy was configured under:  
> `Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy`  
> The settings include a **minimum password length of 12 characters**, as well as password history and lockout policy enforcement. This reflects common enterprise security baselines and helps prevent weak password practices.
> Now the IT department successfully has a GPO implemented.

---



## ✅ Conclusion

This lab simulates common tasks performed by IT Helpdesk and Junior System Administrators in Active Directory environments. From user provisioning to access control and policy enforcement, each step reflects real-world workflows used in enterprise infrastructure. 

Thanks for taking a look at my lab :)
