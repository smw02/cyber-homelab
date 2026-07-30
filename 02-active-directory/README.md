# Active Directory Domain Controller Deployment

## Project Overview

### Objective

Deploy and configure an enterprise Active Directory environment to provide centralized identity management, authentication, and authorization.

### Skills Demonstrated

- Active Directory Domain Services
- DNS Configuration
- Identity Management
- Windows Administration
- Group Policy Management
- User Provisioning


---

# Architecture

## Environment

Hypervisor:
UTM

Operating System:
Windows 11 ARM / Windows Server 2025 ARM

Domain:
corp.local

Domain Controller:
DC01

IP Address:
192.168.10.10


---

# Implementation

## Step 1: Configure Windows Server

- Assign static IP address
  - 192.168.10.10
- Rename computer
  - DC01
- Install Active Directory Domain Services
  - Forest: corp.local
- Promote server to Domain Controller
- Configure DNS
  - 192.168.10.10

## Step 2: Configure Active Directory

- Create Organizational Units
  - IT Staff
- Create users
  - John Smith
  - Sloane Oatmeal
  - Jackson Stewart
  - Samantha Wylie
- Create security groups
  - IT Staff
  - HR Employees
  - Security Analysts


---

# Results

Successfully deployed an Active Directory environment capable of centralized authentication and policy management.
