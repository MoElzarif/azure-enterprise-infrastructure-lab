# 01 - Resource Group

## Purpose

The first step in this lab was to create a dedicated Azure Resource Group to organize all infrastructure components in one place.

A resource group makes it easier to manage, monitor, and clean up all related Azure resources.

---

## Resource Group Details

| Setting | Value |
|---|---|
| Resource Group Name | `rg-enterprise-lab` |
| Region | Canada Central |
| Subscription | Azure for Students |
| Purpose | Central container for all lab resources |

---

## Resources Hosted in This Group

The resource group contains the main components of the Azure Enterprise Infrastructure Lab, including:

- Virtual network
- Subnets
- Network Security Groups
- Linux virtual machine
- Windows Server virtual machine
- Network interfaces
- Public IP addresses
- Managed disks
- Log Analytics Workspace
- Azure Monitor alert rule
- Recovery Services Vault
- Backup configuration

---

## Why This Matters

In a real Azure environment, resource groups are used to keep related resources organized by project, department, application, or environment.

For this lab, keeping everything inside one resource group makes the environment easier to:

- Manage
- Monitor
- Document
- Secure
- Delete when the lab is finished

---

## Evidence

The screenshot below shows the deployed Azure resource group and its resources.

![Resource Group Overview](../screenshots/resource-group/resource-group-overview.png)

---

## Result

A dedicated Azure resource group was successfully created and used as the foundation for the rest of the infrastructure lab.
