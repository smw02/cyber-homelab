# Active Directory Domain Join Guide

## 1. Overview

Joining client computers to an Active Directory domain allows centralized authentication, policy enforcement, and management of organizational endpoints.

This guide documents the process of configuring a Windows client machine and joining it to the `corp.local` Active Directory domain.

### Environment

Domain:
corp.local

Domain controller:
DC01

Domain controller IP:
192.168.10.10

Client Machine: 
WORKSTATION01

Client IP:
192.168.10.20

Technologies Used:

- Windows Client OS
- Active Directory Domain Services
- DNS
- Group Policy
- Windows Firewall


---

## 2. Client Machine Preparation

Before joining the domain, the Windows client was configured to communicate with the Active Directory environment.

Configuration steps:

1. Assigned static IP address: 192.168.10.20
2. Configured DNS server to point to the Domain Controller: Primary DNS (192.168.10.10)
3. Verified network connectivity between client and domain controller.

Testing performed:

- Ping connectivity test (ping 192.168.10.10 / ping 192.168.10.20 )
- DNS resolution test (nslookup corp.local)


Screenshot:

<img width="1440" height="900" alt="Screenshot 2026-07-30 at 4 09 36 PM" src="https://github.com/user-attachments/assets/72517f64-f193-4f8b-bf71-48911c010a85" />


---

## 3. Configure Domain Join Requirements

Before joining the workstation, required Active Directory permissions and network settings were verified.

Requirements:

- Client must use the Domain Controller as its DNS server
- Client must communicate with required Active Directory services
- User account must have appropriate permissions to join a computer to the domain


### Group Policy Configuration

A Group Policy setting was configured to allow authorized users to join computers to the domain.

Configured policy: Add workstations to domain

Purpose:

- Control workstation enrollment permissions
- Maintain administrative control over domain devices


Screenshot:

<img width="1440" height="900" alt="Screenshot 2026-07-30 at 4 15 23 PM" src="https://github.com/user-attachments/assets/f33edd5d-c542-4737-8a22-ac5697302493" />


---

## 4. Join Windows Client to Domain

Steps:

1. Right click Start on `WORKSTATION01`
2. Click: Run
3. Navigate to: sysdm.msc
4. Select: Change
5. Select: Domain
6. Enter: corp.local
7. Provide authorized credentials
8. Restart workstation
   
<img width="1464" height="902" alt="Screenshot 2026-07-30 at 4 21 21 PM" src="https://github.com/user-attachments/assets/8be10172-8cf2-41e3-80da-947561f3c1df" />


---

## 5. Domain Join Validation

After restarting, the workstation was verified as a member of the Active Directory domain.

Validation steps:

Verified:

- Computer object created in Active Directory Users and Computers
- Domain authentication successful
- Group Policy applied successfully
- Client can communicate with Domain Controller


---

## 6. Troubleshooting and Challenges

Several issues were encountered during the domain join process.


---

### Issue 1: DNS Resolution Failure

#### Symptoms:

- Client unable to locate domain controller
- Domain join attempts failed

#### Cause:

Client DNS settings were configured incorrectly.

#### Resolution:

Updated client DNS configuration to point directly to the Domain Controller hosting DNS services.

Correct configuration: Primary DNS 192.168.10.10 - remove alternate DNS


---

### Issue 2: Firewall Restrictions

#### Symptoms:

- ICMP requests failed

#### Cause:

Windows Firewall blocked required network communication.

#### Resolution:

Temporarily modified local firewall settings to allow troubleshooting traffic and verify connectivity.

Future improvement:

Configure specific firewall rules instead of disabling firewall protections.


---

### Issue 3: Domain Join Permissions

#### Symptoms:

- User account unable to add workstation to domain

#### Cause:

Insufficient permissions assigned to the account performing the join.

#### Resolution:

Configured Group Policy permissions to allow authorized users to join computers to the domain.


---

## 7. Lessons Learned

This project reinforced the importance of proper DNS configuration in Active Directory environments.

Key takeaways:

- Active Directory relies heavily on DNS for domain controller discovery and authentication.
- Client devices should use internal DNS servers rather than external DNS providers.
- Group Policy can be used to manage workstation permissions and security settings.
- Troubleshooting should follow a layered approach:
  - Verify IP connectivity
  - Verify DNS resolution
  - Verify authentication
  - Verify policy application


---

## 8. Future Improvements

Potential enterprise enhancements:

- Implement automated workstation deployment
- Use restricted domain join permissions following least privilege principles
- Configure Windows Firewall rules instead of disabling protections
- Implement endpoint monitoring for domain join activity
- Create automated computer provisioning scripts
