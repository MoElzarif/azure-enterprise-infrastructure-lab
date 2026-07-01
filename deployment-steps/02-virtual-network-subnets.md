# 02 - Virtual Network and Subnets

## Purpose

The next step was to create the main Azure Virtual Network for the lab and divide it into separate subnets.

Subnet segmentation is important because it separates different types of workloads and allows different security rules to be applied to each area of the network.

---

## Virtual Network Configuration

| Setting | Value |
|---|---|
| Virtual Network Name | `vnet-enterprise-lab` |
| Address Space | `10.10.0.0/16` |
| Region | Canada Central |
| Resource Group | `rg-enterprise-lab` |

---

## Subnet Design

| Subnet Name | Address Range | Purpose |
|---|---|---|
| `subnet-web` | `10.10.1.0/24` | Public-facing web server subnet |
| `subnet-server` | `10.10.2.0/24` | Reserved for internal server workloads |
| `subnet-management` | `10.10.3.0/24` | Management and administration subnet |

---

## Design Explanation

The virtual network was designed with three separate subnets:

### Web Subnet

The web subnet hosts the Linux Nginx web server. This subnet allows public HTTP traffic through a Network Security Group rule.

### Server Subnet

The server subnet is reserved for future internal server workloads. This allows the lab to be expanded later with additional services such as databases, file servers, or application servers.

### Management Subnet

The management subnet hosts the Windows Server VM. Administrative access is restricted using Network Security Group rules.

---

## Why This Matters

Separating resources into different subnets improves security and organization.

This design makes it possible to:

- Separate public-facing resources from management resources
- Apply different NSG rules to each subnet
- Reduce unnecessary exposure between workloads
- Build a more realistic enterprise-style network layout
- Expand the environment later without redesigning the network

---

## Evidence

The screenshots below show the virtual network and subnet configuration.

![Virtual Network Overview](../screenshots/networking/vnet-overview.png)

![Subnets](../screenshots/networking/subnets.png)

---

## Result

The Azure Virtual Network was successfully created with three subnets for web, server, and management workloads.
