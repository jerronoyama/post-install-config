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

- Log into the osTicket Admin and Agent Panels.
- Understand the difference between the **Admin Panel** and the **Agent Panel**.
- Configure **Roles** to control what agents are allowed to do.
- Configure **Departments** to separate ticket visibility and responsibilities.
- Configure **Teams** that group agents from different departments.
- Configure **User Settings** to control whether registration/login is required to create tickets.
- Add and configure **Agents** (help desk staff).
- Add and configure **Users** (customers/end users).
- Configure **SLA (Service Level Agreements)** for ticket response and resolution times.
- Configure **Help Topics** to categorize the types of tickets users can create.


<h2>Configuration Steps</h2>

### 1. Access osTicket Panels

- Admin/Analyst Login Page: `http://localhost/osTicket/scp/login.php`
- End User Portal: `http://localhost/osTicket/`

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/a9648663-05a5-46f4-a947-649e06e5300d" />

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/daed1ee2-da7a-4e4a-82a6-18309d45783b" />



### 2. Understand Agent Panel vs Admin Panel

- After logging in as an admin/agent, note:
  - **Agent Panel**: Used for working tickets (viewing, responding, managing assignments).
  - **Admin Panel**: Used to configure the system (settings, roles, departments, SLAs, etc.).
- Switch between them using the links usually found at the top-right (e.g., "Admin Panel" / "Agent Panel").

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/5cef0854-7e9f-46f6-8f13-952d9e324864" />

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/85645bba-364e-4214-9899-bd01fc210208" />



### 3. Configure Roles (Grouping Permissions)

- Go to: **Admin Panel → Agents → Roles**
- Click **"Add New Role"**.
- Create a role:
  - Name: `Supreme Admin`
  - Configure permissions as needed (full permissions for lab purposes).

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/4691e3f5-df55-4b04-b98f-47cc8cc1e826" />

<img width="1792" height="1120" alt="Screenshot 2025-11-28 at 6 48 25 PM" src="https://github.com/user-attachments/assets/1c5f8bf4-5287-46fc-9a28-296fe6de9e8d" />



### 4. Configure Departments (Ticket Visibility & Ownership)

- Go to: **Admin Panel → Agents → Departments**
- Click **"Add New Department"**.
- Create a department:
  - Name: `SysAdmins`
  - Adjust visibility, email settings, and assignment settings as needed.

<img width="1792" height="1120" alt="Screenshot 2025-11-28 at 6 51 01 PM" src="https://github.com/user-attachments/assets/a7c59930-95e2-4c5d-9152-657331317488" />
 
<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/4ae1c529-df38-4e04-89ab-5c9a49f920a0" />



### 5. Configure Teams (Cross-Department Groups)

- Go to: **Admin Panel → Agents → Teams**
- Click **"Add New Team"**.
- Create a team:
  - Name: `Online Banking`

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/3e003bbd-8b46-474e-8cc5-a61ea5bc72ae" />
 
<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/32280c7d-53d7-47e4-adca-46edf700d0b6" />



### 6. Configure User Settings (Ticket Creation Requirements)

- Go to: **Admin Panel → Settings → User Settings**
- Adjust user creation and ticket creation behavior:
  - Review the setting for **"Require registration and login to create tickets"** or **"unregistered users can create tickets"**.
  - For the lab, configure according to the instructions (e.g., **registration required** or allow anyone depending on your scenario).

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/0881fdbb-bb26-4737-8669-f1d282f14960" />



### 7. Configure Agents (Help Desk Staff)

- Go to: **Admin Panel → Agents → Add New**
- Create agents (lab example):
  - Agent 1:
    - Name: `Jane`
    - Department: `SysAdmins`
    - Assign appropriate role (e.g., `Supreme Admin` or another role if configured).
  - Agent 2:
    - Name: `John`
    - Department: `Support` (create `Support` department if needed).

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/a8ba77de-ed40-4a8b-ac17-c3006d98da35" />
 
<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/a3557c0b-d32b-4829-8eca-8369e817316e" />
 
<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/7870410e-acb9-4e90-b6a0-74b29629127c" />



### 8. Configure Users (End Users / Customers)

- Switch to: **Agent Panel**
- Go to: **Users → Add New**
- Create a user (lab example):
  - User: `Karen`
- Provide email address and any required details.

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/9688cc8e-b806-45d2-9ca9-a7b98eb7740f" />

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/dbf494f9-ceb2-4cd5-9a60-59f979c2fa77" />


### 9. Configure SLAs (Service Level Agreements)

- Switch back to: **Admin Panel**
- Go to: **Manage → SLA**
- Click **"Add New SLA Plan"** and create:

  1. `Sev-A`
     - Grace Period: `1` hour
     - Schedule: `24/7`
  2. `Sev-B`
     - Grace Period: `4` hours
     - Schedule: `24/7`
  3. `Sev-C`
     - Grace Period: `8` hours
     - Schedule: `Business Hours`

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/fab3ec38-5017-42f1-8590-de84a3ade650" />

<img width="1792" height="1120" alt="image" src="https://github.com/user-attachments/assets/30e57f3f-760e-4d7b-9b26-fb2fcf4c4df6" />



### 10. Configure Help Topics (Ticket Categories)

- Go to: **Admin Panel → Manage → Help Topics**
- Click **"Add New Help Topic"**.
- Create the following help topics:

  - `Business Critical Outage`
  - `Personal Computer Issues`
  - `Equipment Request`
  - `Password Reset`
  - `Other`

📸 *Screenshot: Help Topics list with all topics*  
📸 *Screenshot: Add New Help Topic form*


### 11. Validate Configuration

- Go to the **End User Portal**: `http://localhost/osTicket/`
- Start creating a new ticket and confirm:
  - The configured **Help Topics** appear in the dropdown.
- Log in as an agent and confirm:
  - Departments, Teams, Roles, SLAs, Agents, and Users appear as configured.

📸 *Screenshot: New ticket form showing Help Topics*  
📸 *Screenshot: Agent view of tickets with SLA/Departments visible*
