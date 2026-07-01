# 04 - Virtual Machines

## Purpose

Two Azure virtual machines were deployed for this lab:

- A Linux VM used as a public Nginx web server
- A Windows Server VM used as a management/server administration machine

The goal was to demonstrate basic Azure VM deployment, subnet placement, public/private IP addressing, and secure access using Network Security Groups.

---

## Virtual Machine Summary

| VM Name | Operating System | Purpose | Subnet | Private IP |
|---|---|---|---|---|
| `vm-linux-web01` | Ubuntu Linux 24.04 | Public Nginx web server | `subnet-web` | `10.10.1.4` |
| `vm-win-server01` | Windows Server 2025 | Management/server administration VM | `subnet-management` | `10.10.3.4` |

---

## Linux Web Server VM

The Linux VM was deployed into the web subnet.

### Configuration

| Setting | Value |
|---|---|
| VM Name | `vm-linux-web01` |
| Operating System | Ubuntu Linux 24.04 |
| Subnet | `subnet-web` |
| Private IP | `10.10.1.4` |
| Public IP | Assigned |
| Web Server | Nginx |
| NSG | `nsg-web` |

---

## Nginx Web Server

Nginx was installed on the Linux VM to host a simple public web page.

The web page confirms that:

- The Linux VM is running
- Nginx is installed
- HTTP traffic is allowed through the web NSG
- The public IP can reach the web server

---

## Windows Server VM

The Windows Server VM was deployed into the management subnet.

### Configuration

| Setting | Value |
|---|---|
| VM Name | `vm-win-server01` |
| Operating System | Windows Server 2025 |
| Subnet | `subnet-management` |
| Private IP | `10.10.3.4` |
| Public IP | Assigned |
| NSG | `nsg-management` |

---

## Subnet Placement

The virtual machines were placed into separate subnets based on their role:

| Subnet | VM | Reason |
|---|---|---|
| `subnet-web` | `vm-linux-web01` | Public-facing web workload |
| `subnet-management` | `vm-win-server01` | Administrative/server management workload |
| `subnet-server` | Reserved | Future internal server workloads |

This separation improves organization and allows different security rules to be applied to each workload type.

---

## Access Control

Administrative access was restricted using Network Security Groups:

- SSH to the Linux VM is restricted to an admin public IP
- RDP to the Windows Server VM is restricted to an admin public IP
- HTTP is allowed to the Linux web server for public web access

This avoids exposing administrative ports openly to the internet.

---

## Evidence

### Linux VM Overview

![Linux VM Overview](../screenshots/virtual-machines/linux-overview.png)

### Nginx Website

![Nginx Website](../screenshots/virtual-machines/nginx-website.png)

### Windows VM Overview

![Windows VM Overview](../screenshots/virtual-machines/windows-overview.png)

---

## Result

Both virtual machines were successfully deployed, placed into the correct subnets, and secured using subnet-level Network Security Groups.
