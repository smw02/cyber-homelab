# Active Directory User Management Guide

## 1. Overview

Active Directory user management provides centralized control over user accounts, authentication, authorization, and access to organizational resources.

This guide documents the creation, configuration, and validation of user accounts within the `corp.local` Active Directory environment.

## Environment

Domain:
corp.local

Domain controller:
DC01

## Tools Used:

- Active Directory Users and Computers (ADUC)
- Group Policy Management Console
- Windows Server Active Directory Domain Services


---

# 2. Active Directory Organizational Structure

Before creating user accounts, Organizational Units (OUs) were created to separate users based on organizational roles and simplify administration.

Domain Structure:

corp.local
  Users
  IT Staff
  Security Analysts
  HR Employees

  
Purpose:

- Improve organization of user objects
- Allow targeted Group Policy application
- Simplify administrative tasks


Screenshot:

<img width="1440" height="900" alt="Screenshot 2026-07-30 at 3 44 44 PM" src="https://github.com/user-attachments/assets/b33c3c1a-b6ef-43df-9a51-e5ef86625916" />


---

# 3. Creating User Accounts

User accounts were created using Active Directory Users and Computers.

Steps:

1. Open Server Manager
2. Select Tools
3. Open Active Directory Users and Computers
4. Navigate to the appropriate Organizational Unit
5. Right-click the OU
6. Select: New -> User
7. Enter user information:
- First name
- Last name
- Username
- Password
8. Configure account settings
9. Complete user creation


---

# 4. Configuring User Account Settings

After account creation, user properties were configured.

Configured settings:

- Department information
- Group membership
- Account restrictions
- Password requirements

Account options:

- User must change password at next login
- Account expiration dates

Screenshot:

<img width="1552" height="903" alt="Screenshot 2026-07-30 at 3 48 02 PM" src="https://github.com/user-attachments/assets/a1184e2d-d39c-4010-a4bd-6ce88b5b9abd" />


---

# 5. Creating Security Groups

Security groups were created to manage permissions based on job responsibilities.

Purpose:

- Simplify access management
- Follow least privilege principles
- Avoid assigning permissions directly to individual users

Steps:

1. Open Active Directory Users and Computers
2. Navigate to Security Groups OU
3. Right-click: New -> Group
4. Configure:
  - Group name
  - Group scope
  - Group type

Screenshot:

<img width="1552" height="903" alt="Screenshot 2026-07-30 at 3 52 42 PM" src="https://github.com/user-attachments/assets/b77dc7cb-33d3-42c9-8d32-5746ff6ed64b" />


---

# 6. Assigning Users to Groups

Users were assigned membership based on organizational roles.

Steps:

1. Open user properties
2. Select: Member of
3. Click: Add
4. Select appropriate Security Group


---

# 7. User Account Validation

User accounts were tested to verify proper functionality.

Validation steps:

Verified:

- User can authenticate to the domain
- User receives appropriate group memberships


---

# 8. Lessons Learned

- Understanding OU design
- Managing group permissions
- Troubleshooting authentication issues
- Applying least privilege principles
