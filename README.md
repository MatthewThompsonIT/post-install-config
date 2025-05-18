<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- [Allow Anyone to Create a Ticket](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#allow-anyone-to-create-a-ticket)
- [Configure Roles (for grouping permissions)](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-roles-for-grouping-permissions)
- [Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-departments-ticket-visibility-help-desk-vs-sysadmins-vs-networking)
- [Configure Teams](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-teams)
- [Configure Agents (workers)](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-agents-workers)
- [Configure Users (customers)](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-users-customers)
- [Configure SLA](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-sla)
- [Configure Help Topics (For when users create a ticket)](https://github.com/MatthewThompsonIT/post-install-config/blob/main/README.md#configure-help-topics-for-when-users-create-a-ticket)

>[!NOTE]
> The Admin/Analyst Login Page: http://localhost/osTicket/scp/login.php 
> End Users osTicket URL: http://localhost/osTicket 

<h2>Allow Anyone to Create a Ticket</h2>

- Lets start by logging into the admin panel
- Click on "Settings"
- Click on "User Settings"
- Ensure the box next to "Registration Required" is UNCHECKED

![image](https://github.com/user-attachments/assets/061ad545-dc57-4d69-93b6-f7a3b0741837)


<h2>Configure Roles (for grouping permissions)</h2>

<p>


- Open the Admin Panel
  - Click on Agents at the top
  - Click on "Roles"
  - Click "+ Add New Role"

![image](https://github.com/user-attachments/assets/ad0fbb6e-aa2e-4782-9b32-75ecea7406ea)

- Name the role "Supreme Admin"
- Click on Permissions

![image](https://github.com/user-attachments/assets/8270f9c6-9ce0-490c-bd40-6ab16f54b0fd)

- Check all the boxes on all three tabs (Tickets, Tasks, Knowledgebase)
- Click on "Add Role"

![image](https://github.com/user-attachments/assets/3f33ac52-3b29-4b0e-9842-d54b318995e8)

<h2>Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)</h2>

- Go back to the Admin Panel
- Click on "Agents"
- Click on "Departments"
- Click "+ Add New Department"

![image](https://github.com/user-attachments/assets/0d39ba89-2081-49fc-aa86-d65cdd42b0d4)


- Name the Department "SysAdmins"
- Leave everything else default

> [!NOTE]
> Ensure the "Parent" is set to " -- Top-Level Department -- "

- (Ignore the "Access" tab for now, we dont have any agents to add yet)
- Click "Create Dept"

<h2>Configure Teams</h2>

- Go back to the Admin Panel
- Click on "Agents"
- Click on "Teams"
- Click "+ Add New Team"

![image](https://github.com/user-attachments/assets/b48b1425-b5ee-4389-97fa-84a3a41034fa)

- Name it "Online Banking"
- Leave everything else default
- (Skip "Members" for now as we havent created any yet)
- Click "Create Team"

![image](https://github.com/user-attachments/assets/59465038-ea0e-4b87-a38e-510676841c1a)

<h2>Configure Agents (workers)</h2>

- Go back to the Admin Panel
- Click on "Agents"
- Click "+ Add New"

![image](https://github.com/user-attachments/assets/0bc37068-b793-47c0-8f07-8f7418ffc5dc)

- Create two agents
  - Name: Jane Doe
  - Email Address: jane@janedoe.com (This is a fake email and you can make it anything)
  - Username: Jane
  - Click on "Set Password"
 
![image](https://github.com/user-attachments/assets/3f3e5235-9486-4510-b18c-78350ebcc62c)

  - Uncheck "Send the agent a password reset email"
  - Set the password to whatever you want (Password1)
  - Uncheck "Require password change at next login"
  - Hit "Update"

![image](https://github.com/user-attachments/assets/e5d16331-3528-4633-9d20-304680109e18)

  - Click on "Access"
  - Make Jane a SysAdmin and Supreme Admin

  ![image](https://github.com/user-attachments/assets/c9d9b46b-1b64-4d2c-8139-bf1ad64440e4)

  - Skip Permissions
  - Click on "Teams"
  - Add Jane to the "Online Banking" team
  - Click "Create"
 
  ![image](https://github.com/user-attachments/assets/9f1a8522-3336-4d58-92bf-383a6eafab55)

- Go back to the Admin Panel
- Click on "Agents"
- Click "+ Add New"
  - Name: John Doe
  - Email Address: john@johndoe.com (This is a fake email and you can make it anything)
  - Username: John
  - Click on "Set Password"

![image](https://github.com/user-attachments/assets/3f3e5235-9486-4510-b18c-78350ebcc62c)

  - Uncheck "Send the agent a password reset email"
  - Set the password to whatever you want (Password1)
  - Uncheck "Require password change at next login"
  - Hit "Update"

![image](https://github.com/user-attachments/assets/e5d16331-3528-4633-9d20-304680109e18)

  - Click on "Access"
  - Make John a "Support" agent and give him "View Only" Access

![image](https://github.com/user-attachments/assets/832703f1-031d-469e-a3a9-d572ed9be35b)

  - Leave Everything else Default
  - Hit "Create"

<h2>Configure Users (customers)</h2>

- Go back to the Admin Panel
- Click on "Users"
- Click "+ Add User"

![image](https://github.com/user-attachments/assets/5711e3eb-1331-4c6f-9ef4-75de82adf664)

- Create two Users
    - Karen
      - Email: karen@gmail.com (This is a fake email and you can make it anything)
      - Full Name: Karen
    - Ken
      - Email: ken@gmail.com (This is a fake email and you can make it anything)
      - Full Name: Ken

<h2>Configure SLA</h2>

- Go back to the Admin Panel
- Click on "Manage"
- Click on "SLA"
- Click "+ Add New SLA Plan"

![image](https://github.com/user-attachments/assets/3c641e9a-fdeb-481e-854f-838f157bce0f)

- Change the name to "Sev-A"
- Enter "1" for Grace Period
- Change Schedule to "24/7"
- Click "Add Plan"

![image](https://github.com/user-attachments/assets/fc2b1a77-5e38-4fe9-aaf2-aa99ee9056e6)

- Create another SLA Plan
- Change the name to "Sev-B"
- Enter "4" for Grace Period
- Change Schedule to "24/7"
- Click "Add Plan"

![image](https://github.com/user-attachments/assets/17b120d1-fcce-4180-a8e6-5b6f6988d7fc)

- Create another SLA Plan
- Change the name to "Sev-C"
- Enter "8" for Grace Period
- Change Schedule to "Monday - Friday 8am - 5pm with U.S Holidays"
- Click "Add Plan"

![image](https://github.com/user-attachments/assets/a270bc44-5e93-4547-98a4-021908079c76)

<h2>Configure Help Topics (For when users create a ticket)</h2>

- Head back to the Admin Panel
- Click on "Manage"
- Click on "Help Topics"
- Click "+ Add New Help Topic

![image](https://github.com/user-attachments/assets/728df8dc-3fe2-4a4c-921b-e59a9f6ded39)

- Change the name to "Business Critical Outage"
- Change "Parent Topic" to "Report a Problem"
- Hit "Add Topic"

![image](https://github.com/user-attachments/assets/d3fc1e33-9f52-43af-9f9f-1cbdab82fee4)

- Head back to the Admin Panel
- Click on "Manage"
- Click on "Help Topics"
- Click "+ Add New Help Topic
    - Change the name to "Personal Computer Issues"
    - Change "Parent Topic" to "Report a Problem"
    - Hit "Add Topic"

![image](https://github.com/user-attachments/assets/3f993327-3f3a-45b7-bd65-a6461f12a7d8)

- Head back to the Admin Panel
- Click on "Manage"
- Click on "Help Topics"
- Click "+ Add New Help Topic
    - Change the name to "Equipment Request"
    - Change "Parent Topic" to "General Inquiry"
    - Hit "Add Topic"

![image](https://github.com/user-attachments/assets/d18f554d-bb22-4b4b-94a7-689fba8aaacc)

- Head back to the Admin Panel
- Click on "Manage"
- Click on "Help Topics"
- Click "+ Add New Help Topic
    - Change the name to "Password Reset"
    - Change "Parent Topic" to "Report a Problem"
    - Hit "Add Topic"

![image](https://github.com/user-attachments/assets/110404f8-ee24-4da4-8327-f7a7e487e88d)

- Head back to the Admin Panel
- Click on "Manage"
- Click on "Help Topics"
- Click "+ Add New Help Topic
    - Change the name to "Other"
    - Change "Parent Topic" to "General Inquiry"
    - Hit "Add Topic"

![image](https://github.com/user-attachments/assets/ad4e1b6f-a4a7-4f78-af9e-7d8ce4f84bef)




</p>
</br>










