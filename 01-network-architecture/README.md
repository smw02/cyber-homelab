# Network Architecture

## Project Overview

### Objective

Plan and create an Enterprise network architecture.

### Skills Demonstrated

- Network diagram design
- IP addressing and subnetting
- Virtualization deployment


---

# Architecture

## Environment


- Operating System: macOS
- Virtualization Platform: UTM
- Drawing application: draw.io


## Architecture Diagram


See Network Diagram.drawio.pdf


---

# Implementation

## Step 1: Preparation

- Install draw.io
- Determine number of devices
- Install UTM

## Step 2: Configuration

- 1 subnet, 1 DC, 1 client, 1 Wazuh server, 1 Kali machine, 1 pfSense firewall

## Step 3: Deployment

- Utilized /24 subnet to create single subnet for all devices and avoid having to use a default gateway in order to isolate from my 
personal network
- Installed UTM for macOS, downloaded Windows Server 2025 & Windows 11 pro images for use in virtualization
- Configured UTM to use a shared network to ensure virtual machines are not connecting over host device network
- Installed drawio and created simple network diagram including planned IP addresses
- Exported PDF from drawio to commit to repository

---

# Challenges and Troubleshooting

- Windows Server 2025 does not have an ARM based image available publicly anymore, was able to find an old copy for eval purposes

---

# Lessons Learned

Learned about how to utilize github in a more professional manner, ISO download/deployment, different virtualization methods, importance
of ARM architecture compatibility.

