# Azure Enterprise Infrastructure Lab

## Project Overview

This project demonstrates the deployment of a small enterprise-style infrastructure environment in Microsoft Azure. The lab includes networking, subnet segmentation, virtual machines, network security groups, monitoring, backup protection, and a public Linux web server.

The goal of this project is to show hands-on Azure administration skills that are relevant to cloud administrator, system administrator, and junior cloud engineer roles.

---

## Architecture Summary

The environment was built inside a single Azure resource group and organized using a hub-style virtual network with separate subnets for different workloads.

### Network Design

| Component | Configuration |
|---|---|
| Virtual Network | `vnet-enterprise-lab` |
| Address Space | `10.10.0.0/16` |
| Web Subnet | `subnet-web` - `10.10.1.0/24` |
| Server Subnet | `subnet-server` - `10.10.2.0/24` |
| Management Subnet | `subnet-management` - `10.10.3.0/24` |

### Virtual Machines

| VM Name | Operating System | Purpose | Subnet |
|---|---|---|---|
| `vm-linux-web01` | Ubuntu Linux 24.04 | Public Nginx web server | `subnet-web` |
| `vm-win-server01` | Windows Server 2025 | Management / server administration VM | `subnet-management` |

### Security Design

| NSG | Purpose |
|---|---|
| `nsg-web` | Allows public HTTP traffic to the Linux web server and restricts SSH access to an admin IP |
| `nsg-management` | Restricts RDP access to the Windows Server VM to an admin IP |
| `nsg-server` | Reserved for internal server workload rules |

---

## Technologies Used

- Microsoft Azure
- Azure Virtual Network
- Azure Subnets
- Network Security Groups
- Ubuntu Linux 24.04
- Windows Server 2025
- Nginx Web Server
- Azure Monitor
- Log Analytics Workspace
- Azure Alerts
- Recovery Services Vault
- Azure Backup
- GitHub Documentation

---

## What Was Built

This lab includes:

- A dedicated Azure resource group for all lab resources
- A virtual network with three segmented subnets
- Subnet-level Network Security Groups
- A Linux VM running Nginx as a public web server
- A Windows Server VM placed in a management subnet
- Restricted administrative access using NSG rules
- Azure Monitor alerting for high CPU usage
- A Log Analytics Workspace for monitoring data
- A Recovery Services Vault for VM backup
- Screenshot evidence for each major Azure component

---

## Project Evidence

### Resource Group

The full lab environment was deployed inside a single resource group.

![Resource Group Overview](screenshots/resource-group/resource-group-overview.png)

---

### Virtual Network

The virtual network was created with separate subnets for web, server, and management workloads.

![Virtual Network Overview](screenshots/networking/vnet-overview.png)

![Subnets](screenshots/networking/subnets.png)

---

### Linux Web Server

The Linux VM was deployed into the web subnet and configured with Nginx.

![Linux VM Overview](screenshots/virtual-machines/linux-overview.png)

![Nginx Website](screenshots/virtual-machines/nginx-website.png)

---

### Windows Server VM

The Windows Server VM was deployed into the management subnet.

![Windows VM Overview](screenshots/virtual-machines/windows-overview.png)

---

### Network Security Groups

The web NSG allows HTTP traffic to the Linux web server and restricts SSH access to an admin IP.

![Web NSG Rules](screenshots/security/nsg-web.png)

The management NSG restricts RDP access to an admin IP.

![Management NSG Rules](screenshots/security/nsg-management.png)

The server NSG is reserved for internal server workloads.

![Server NSG Rules](screenshots/security/nsg-server.png)

---

### Monitoring

Azure Monitor was configured with a high CPU alert rule.

![High CPU Alert](screenshots/monitoring/high-cpu-alert.png)

---

### Backup

Azure Backup was configured using a Recovery Services Vault.

![Backup Success](screenshots/backup/backup-success.png)

---

## Deployment Documentation

The deployment process is documented in the `deployment-steps` folder:

| File | Description |
|---|---|
| `01-resource-group.md` | Resource group creation |
| `02-virtual-network-subnets.md` | Virtual network and subnet design |
| `03-network-security-groups.md` | NSG rules and security configuration |
| `04-virtual-machines.md` | Linux and Windows VM deployment |
| `05-monitoring.md` | Azure Monitor and alerting |
| `06-backup.md` | Recovery Services Vault and backup |
| `07-cleanup.md` | Cleanup process to avoid unnecessary cost |

---

## Skills Demonstrated

This project demonstrates the following skills:

- Azure resource organization
- Virtual network planning
- Subnet segmentation
- Network Security Group configuration
- Linux server deployment
- Windows Server deployment
- Basic web server configuration with Nginx
- Public and private IP understanding
- Azure Monitor alerting
- VM backup configuration
- Cloud infrastructure documentation
- GitHub project presentation

---

## Important Notes

This is a lab environment created for learning and portfolio purposes. It is not a production high-availability architecture.

The project focuses on core Azure administration skills, including infrastructure deployment, networking, security rules, monitoring, and backup.

---

## Future Improvements

Planned improvements are documented in:

[future-improvements.md](future-improvements.md)

---

## Lessons Learned

Key lessons from this project are documented in:

[lessons-learned.md](lessons-learned.md)
