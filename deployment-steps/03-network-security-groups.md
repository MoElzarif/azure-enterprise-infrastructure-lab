# 03 - Network Security Groups

## Purpose

Network Security Groups were configured to control inbound and outbound traffic for the lab environment.

NSGs are important because they act as traffic filters for Azure subnets and network interfaces. They help control which ports are exposed and which sources are allowed to connect.

---

## NSG Design

| NSG Name | Associated Subnet | Purpose |
|---|---|---|
| `nsg-web` | `subnet-web` | Controls access to the Linux Nginx web server |
| `nsg-management` | `subnet-management` | Controls administrative access to the Windows Server VM |
| `nsg-server` | `subnet-server` | Reserved for internal server workload rules |

---

## Web NSG Rules

The web subnet hosts the Linux Nginx web server. The NSG allows public HTTP traffic and restricts SSH access to an admin public IP.

| Rule Name | Port | Protocol | Source | Action | Purpose |
|---|---:|---|---|---|---|
| `Allow-HTTP` | 80 | TCP | Any | Allow | Allows users to access the Nginx web page |
| `Allow-SSH-Admin` | 22 | TCP | Admin public IP only | Allow | Allows SSH administration from a trusted IP |

---

## Management NSG Rules

The management subnet hosts the Windows Server VM. The NSG restricts RDP access to an admin public IP.

| Rule Name | Port | Protocol | Source | Action | Purpose |
|---|---:|---|---|---|---|
| `Allow-RDP-Admin` | 3389 | TCP | Admin public IP only | Allow | Allows remote administration of the Windows Server VM |

---

## Server NSG

The server subnet is reserved for future internal workloads.

In a larger environment, this subnet could be used for:

- Internal application servers
- Database servers
- File servers
- Domain services
- Backend systems

The server subnet would normally avoid direct public internet exposure and only allow required internal traffic.

---

## Security Explanation

This lab uses subnet-level NSG association instead of placing NSGs directly on each network interface.

This makes the design cleaner because all resources inside a subnet inherit the same subnet-level security rules.

The security model follows this basic approach:

- Public web traffic is only allowed on HTTP port 80
- SSH is restricted to an admin IP
- RDP is restricted to an admin IP
- Default Azure deny rules block unwanted inbound traffic
- Management access is separated from the public web subnet

---

## Why This Matters

In real Azure environments, NSGs are used to reduce the attack surface of cloud resources.

This lab demonstrates:

- Least privilege access
- Restricted administrative access
- Subnet-level traffic control
- Separation between public and management workloads
- Safer exposure of cloud virtual machines

---

## Evidence

The screenshots below show the configured NSG rules.

### Web NSG

![Web NSG Rules](../screenshots/security/nsg-web.png)

### Management NSG

![Management NSG Rules](../screenshots/security/nsg-management.png)

### Server NSG

![Server NSG Rules](../screenshots/security/nsg-server.png)

---

## Result

Network Security Groups were successfully configured to protect the web, management, and server subnets.
